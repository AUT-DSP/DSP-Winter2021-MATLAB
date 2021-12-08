<div align="center">
<i>In The Name Of God</i>

<p>
  <img src="https://user-images.githubusercontent.com/47852354/138564509-b5dffb4e-f48b-4db5-b8a4-1385ef2b22c8.png" width="200">
</p>

# Dicrete-time Signal Processing - MATLAB HW2
### Deadline: Friday, 2021 Dec.10 - 23:59 (GMT+3:30)
---
**Dr. Hamid Sheikhzadeh - TAs: Arshia Samoudi - Saleh Tabatabaei**
</div>

# Introduction
Hi everyone.

HW2 Consists of 6 Questions:
- Q1,Q2 : Chapter 4 (Sampling,Reconstruction)
- Q3,Q4,Q5 : Chapter 5
- Q6 : Chapter 6

Q1,Q2 Tests Your Abilities in Following Content:
- Sampling
- Reconstruction
- DownSampling
- UpSampling
- Aliasing

Please **Read Submission** and Do all Theoretical and Coding Parts of Exercises and Publish your Work just like The **MATLAB HW-Template** given as Follows and Upload it in [Courses](https://courses.aut.ac.ir/)

Good Luck!


<br>

# MATLAB Coding Exercises
<br>

## Q1. RECONSTRUCTION
### A. Sampling
1. Write a MATLAB program to Plot following Signals, where f = 10hz and the Time interval is [0,0.2]:(*Hint: Use `sawtooth` Command*)

	<img src="https://render.githubusercontent.com/render/math?math=y = sin(2\pi ft) %2Bcos(4\pi ft)"><br/>
	
	
	<img src="https://render.githubusercontent.com/render/math?math=y = sawtooth(2\pi ft)">


2. Sample These Signals with Sampling Frequency 100Hz and discuss about the boundrys of Sampling Frequency in your Report. 
### B. Interpolation
A reconstruction filter on the output of a sampled data system. Provided the signal was sampled at a rate greater than twice the highest frequency present in the original, the output of a reconstruction filter will be identical to the original signal.

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141496372-d04b22ff-0ee4-49f8-8e89-103faf3dcc75.png">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141496380-7da2e1eb-4c37-456d-9c04-a0b4ce46ae35.png">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141496389-4708ccec-01c9-4441-a4ab-76f848917383.png" width = "500">
</p>

#### 1. Linear Interpolation
1. In Linear interpolation, the samples are simply connected to each other with strict line. Write a MATLAB program to compute Linear Interpolated Signals:(*Hint: interp1 Command*). ts is interval with step of inv(fs). for this part consider inv(2fs) as the step of tnew and plot ynew and compare it with ys.

		ynew = interp1(ts,ys,tnew,"linear")

the `plot` function of MATLAB also uses Linear Interpolation. plot(ts,ys) will connect ys samples with strict line. `interp1` can be used for sampling too and Assigns signals values to the new timeline. use following command for sampling signal with fs:(similar to Q1.A)

	     ys = interp1(t,y,ts,"linear")
		
where ts is time interval with inv(fs) as step.

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141498962-ce2d0ea1-0253-4a34-b2bb-e194bdb1e45f.png" width = "300">
</p>


#### 2. Sinc Interpolation
1. Write a MATLAB program to compute Reconstructed Signals Obtained From sinc interpolation.(Reconstruct ys.**Q1 folder clip**)

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141498118-04e1e5cf-3761-42b7-a733-5e2296199849.png" width = "300">
</p>

2. Consider different values for sampling frequency and check that whether the Reconstruction is possible or not. mention the results in your Report.
3. Compare the Reconstructed Signal with the Original one and state that where Maxima of Error happens.
4. is it possible to reconstruct all form of signals? explain the Error cause of sawtooth Reconstructed signal.


#### 3. Additional Content: Polynomial Interpolation
The Lagrange interpolation is given mathematically by


<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141500158-4e3116d7-27cf-4479-9143-9755676ab718.png" width = "170">
</p>

where x(tk) is the value of the sample at instant tk and Lk(t) is the interpolating polynomial term multiplied by each sample value, and is given by

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141500210-8f489a10-6541-465c-9f02-b771ef634ca1.png" width = "400">
</p>


Note that the terms on the numerator are of the form (t − tk), and the terms on the denominator are of the form (tk − ti), with the single term (tk − tk) removed from both the numerator and denominator. At the sample time t = tk (corresponding to the current “center” of interpolation), the interpolating function Lk(tk) = 1 because the numerator will equal the denominator. 

At time instants corresponding to one of the other known samples, say, t = tk + 1, one of the numerator terms will be zero, and thus the interpolating function Lk(tk + 1) = 0. Therefore, the interpolation is guaranteed to pass through the known samples with weighting of one:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141500256-271d80ba-9aab-4b59-990c-5f278a02867e.png" width = "200">
</p>


## Q2. App Designer - UpSampling & DownSampling
### A. Downsampling
The sampling rates of a discrete-time signal are changed using operators called decimators and interpolators. A decimator consists of a cascade of a lowpass filter, and a downsampler (or subsampler), denoted by ↓ N.

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141604564-35330ca9-28a6-496a-8a45-10eaa0349c3f.png" width = "400">
</p>

In the frequency domain, the input and the output of the downsampler are related by

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=Y\left(e^{j\omega}\right)=\frac{1}{N}\sum_{r=0}^{N-1}X\left(e^{j\left(\frac{\omega}{N}%2B\frac{2\pi r}{N}\right)}\right)" width = "300">
</p>

Downsampling introduces aliasing into the DTFT of x[n]. The downsampler is the basic component for sampling rate reduction.

MATLAB Command for Downsampling is `downsample(x,M)`

### B. Upsampling
The dual operation is called interpolation. It is the process by which a signal sampled at one sampling rate is converted to one with a rate that is L times higher. upsampler, inserts L - 1 zeros between each sample in the input. The first subsystem, which is called an upsampler, inserts L - 1 zeros between each sample in the input. The second subsystem is a lowpass filter with a gain of L and a cutoff frequency of <img src="https://render.githubusercontent.com/render/math?math=\frac{\pi}{L}">
. 


<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141604707-4cbb812e-360b-4568-b371-98065da3d9d1.png" width = "400">
</p>

MATLAB Command for Upsampling is `upsample(x,L)`.

### C. APP Designer
By the Definition of Upsampling and Downsampling, Design an App according to the clip in **Q2 folder** that show the rate factor effect of the input sequence `x[n] = sinc((n-M/2)/(2N)).^2` for n=0,1,…,M-1, M = 300, in frequency Domain

- N: the bandwidth factor of tri(f) which is <img src="https://render.githubusercontent.com/render/math?math=\frac{\pi}{N}">
- L: the Upsampler factor
- M: the downsampler factor
- w: filter normalized cut-off frequency (for creating filter use `fir1` command in MATLAB)

```
b = fir1(filter Order, Normalized cut-off frequncy)
Hint: let Order Filter be half of the length of input you want to filter.
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141605250-7186b30d-4a32-44af-9fed-6cad6e1bf810.png" width = "400">
</p>


### Additional Content
the `resample` Command in MATLAB allows you to Not only have rational sampling Factor but also Does the Filtering Part too! 


## Q3. Transform Analysis of Linear Time-Invariant Systems
### Decomposition Theorem 
from this Theory we know that a system x[n] can be decomposed to Two Min-phase and All-pass system **with one Condition!**.

1. for **Real** system with zeros on <img src="https://render.githubusercontent.com/render/math?math=z1 = 0.4e^{(j\frac{\pi}{6})}"> and  <img src="https://render.githubusercontent.com/render/math?math=z2 = 1.5e^{(j\frac{2\pi}{3})}"> (*System's coefficients are **Real** therefore you must consider `conj(z1)` and `conj(z2)` as your system's zeros too*)

	a) determine the Min-phase and All-pass System of The specified system theoretically. use `zplane` to show the Zeros and Poles of determined systems.
	
	b) Using MATLAB, show the relation between phase and groupdelay of system with it's decomposed parts. (*for groupdelay use `grpdelay` command.*)

2. Consider the Zeros above for a FIR GLP type 3 System.

	a) is it possible to use the Decomposition Theorem? why?
	
	b) is it possible to Compensate the amplitude distortion? Write MATLAB Code to approximately Compensate the amplitude distortion. (*Hint: Min-Max-Uc Decomposition*) 
	
	**(Bonus)  c) there is a practical way to Compensate the amplitude distortion. what you think it is?**

	
## Q4. Symmetries and Filter Types
### Orthogonal FIR Filters

Two filters A(z) and B(z) are orthogonal if:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143774450-73d21eea-d9fc-48e8-ad66-cfc4b5b0078d.png" width = "200">
</p>

where a(n) are the coefficients of A(z), and b(n) are the coefficients of B(z).

a) find the relation between A(z) and B(z). for given A(z), what would be the B(z)?

b) for given sequence h0 = [1 2 3 4 5 6], determine the orthogonal filter. plot frequency response of both filter and compare them.


### Mirror FIR Filters

Given a symmetric FIR filter H0(z), a mirror filter H1(z) can be easily obtained by sign alternation:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143774408-1a65eb47-a593-4d17-a3ff-63aa0dd1317a.png" width = "180">
</p>

c) what is the relation between H1(z) and H0(z) frequency response?

d) for given sequence h0 = [1 3 1 4 1 3 1], determine the Mirror filter. plot frequency response of both filter and compare them.



## Q5. Multi-Channel Filters and Perfect Reconstruction
### A. Two-Channel Filters

#### Basic Equations for the Two-Channel Filter Bank

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143775684-9e311b10-7541-4001-bdd6-ddc31c798926.png" width = "530">
</p>

Let us study the two-channel filter bank represented in Fig. above. H0(z) and H1(z) form an analysis filter bank, and F0(z) and F1(z) form a synthesis
filter bank. H0(z) and F0(z) are low-pass filters, while H1(z) and F1(z) are high-pass filters.
The output of the two-channel filter bank is:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143775751-1110a253-b2cb-441a-8ff9-738d777571a1.png" width = "350">
</p>

The term with U(−z) is called the **alias term**. In order not to have any contribution of U(−z) to the filter bank output, the following condition must be met:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143775821-bfc199ea-0393-4ba0-af15-397a265613f3.png" width = "250">
</p>
This is the **aliasing cancellation condition**.

The term with U(z) in Eq.(1.70) is called the **distortion term** and for perfect reconstruction must be a constant or a pure delay (depending on we were working
with non-causal filters or with causal filters). Therefore, the distortion term must be one of the following:

- Off-line work, non-causal filters:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143776001-a6b244a7-2541-4e0e-9a40-cf5f7a40a78c.png" width = "250">
</p>

- On-line work, causal filters:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143776019-ee2f29ce-6977-4eb5-a1a6-bc9294a8f113.png" width = "250">
</p>

### B. Four-Channel Filters

Consider the Block Below:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143776134-99ae93b9-d14a-4d4b-acb2-451d7ee19db9.png" width = "450">
</p>

this is the structure of Four-Channel Filters with one process unit. we are about to get familiar with one of Application of Multi-rate Filters.

a) Consider x(t) as your input:

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/143776258-9c42a44f-aff2-42af-8f48-56fa8b5dd4d6.png" width = "450">
</p>

plot the frequency response of x(t).

b) by using the `xlsread`, `readtable` or similar Commands, import the coefficients of analysis filter bank, and synthesis filter bank. (**Q5 folder**)

**Note: coefficients of analysis filter bank are in sheet1 and synthesis filter bank coefficients are in sheet2. each consist of 4 * 32 matrix**

c) with this filter bank:

- double the first Frequency component
- eliminate the second Frequency component
- the third Frequency component Remain unchanged
- attenuate the fourth Frequency component by 0.5 factor

and plot the frequency response.



## Q6. Structure for Discrete-Time System
### Equalizer

In this problem we are going to design an equalizer system for a given channel system function which has been estimated beforehand. Load the ‘a.mat’ and ‘b.mat’ files which are the denominator and numerator coefficient of the estimated system function of the channel(Files are located in **Q6 Folder**). 

#### 1- plot the frequency response of the channel magnitude and phase (`freqz` would be helpful). 
#### 2- plot the pole-zero locations of the channel system function. 
#### 3- read a short audio file using ‘audioread’ command in matlab and plot it’s frequency spectrum magnitude and phase. 

#### 4- use your file as the input of the channel and plot the output in time domain and frequency domain (magnitude and phase). 
#### 5- we want to design an equalizer to compensate the frequency amplitude distortion of the channel. Design that equalizer and plot the location of its zeros and poles and also the frequency response of the equalizer(magnitude and phase). 
#### 6- plot the frequency response of the overall system of channel followed by your equalizer(magnitude and phase). 
#### 7- in this part we want to analyze the effect of quantization of the coefficients of digital filters and the effect of the implementation methods. 
Write a function in matlab and name it quantize_m which receives a vector of numbers and extract the dynamic range of the vector which is the difference between the minimum and maximum of that vector, and also receives n_bit parameter which is the number of bits that our system is going to use. The output is the quantized vector. 
#### 8- quantize the coefficients of your equalizer according to direct form II with 4,8,16,32 bits and plot the pole zero locations for each number of bits in one plot.(use `subplot`) 
Do you notice something dangerous when using few bits? 
What is the minimum number of bits that puts the poles and zeros in acceptable positions?4or 8 or 16 or 32? 




----
**Amirkabir University of Technology, Electrical Engineering Department**
















