<div align="center">
<i>In The Name Of God</i>

<p>
  <img src="https://user-images.githubusercontent.com/47852354/138564509-b5dffb4e-f48b-4db5-b8a4-1385ef2b22c8.png" width="200">
</p>

# Dicrete-time Signal Processing - MATLAB HW2
### Deadline: Friday, 2021 Dec.4 - 23:59 (GMT+3:30)
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
1. Write a MATLAB program to compute following Signals, where f = 10hz and the Time interval is [0,0.2]:

	<img src="https://render.githubusercontent.com/render/math?math=y = sin(2\pi ft) %2Bcos(4\pi ft)"><br/>
	
	
	<img src="https://render.githubusercontent.com/render/math?math=y = sawtooth(2\pi ft)">


2. Sample These Signals with Sampling Frequency 100Hz and discuss about the boundrys of Sampling Frequency in your Report and in your MATLAB code. 
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
1. In Linear interpolation, the samples are simply connected to each other with strict line. Write a MATLAB program to compute Linear Interpolated Signals:(*Hint: interp1 Command*)

		vq = interp1(x,v,xq,"linear")


<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/141498962-ce2d0ea1-0253-4a34-b2bb-e194bdb1e45f.png" width = "300">
</p>



#### 2. Sinc Interpolation
1. Write a MATLAB program to compute Reconstructed Signals Obtained From sinc interpolation.(**Q1 folder clip**)

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


## Q6. Structure for Discrete-Time System
### Equalizer

In this problem we are going to design an equalizer system for a given channel system function which has been estimated beforehand. Load the ‘a.mat’ and ‘b.mat’ files which are the denominator and numerator coefficient of the estimated system function of the channel(Files are located in **Q6 Folder**). 

##### 1- plot the frequency response of the channel magnitude and phase (`freqz` would be helpful). 
##### 2- plot the pole-zero locations of the channel system function. 
##### 3- read a short audio file using ‘audioread’ command in matlab and plot it’s frequency spectrum magnitude and phase. 

##### 4- use your file as the input of the channel and plot the output in time domain and frequency domain (magnitude and phase). 
##### 5- we want to design an equalizer to compensate the frequency amplitude distortion of the channel. Design that equalizer and plot the location of its zeros and poles and also the frequency response of the equalizer(magnitude and phase). 
##### 6- plot the frequency response of the overall system of channel followed by your equalizer(magnitude and phase). 
##### 7- in this part we want to analyze the effect of quantization of the coefficients of digital filters and the effect of the implementation methods. 
Write a function in matlab and name it quantize_m which receives a vector of numbers and extract the dynamic range of the vector which is the difference between the minimum and maximum of that vector, and also receives n_bit parameter which is the number of bits that our system is going to use. The output is the quantized vector. 
##### 8- quantize the coefficients of your equalizer according to direct form II with 4,8,16,32 bits and plot the pole zero locations for each number of bits in one plot.(use `subplot`) 
Do you notice something dangerous when using few bits? 
What is the minimum number of bits that puts the poles and zeros in acceptable positions?4or 8 or 16 or 32? 




----
**Amirkabir University of Technology, Electrical Engineering Department**
















