<div align="center">
<i>In The Name Of God</i>

<p>
  <img src="https://user-images.githubusercontent.com/47852354/138564509-b5dffb4e-f48b-4db5-b8a4-1385ef2b22c8.png" width="200">
</p>

# Dicrete-time Signal Processing - MATLAB HW1
### Deadline: Friday, 2021 Nov.8 - 23:59 (GMT+3:30)
---
**Dr. Hamid Sheikhzadeh - TAs: Arshia Samoudi - Saleh Tabatabaei**
</div>

# Introduction
Hi everyone.
MATLAB Homework 1 Tests Your Abilities in Following Content:
- Convolution
- Impulse Respones
- Frequency Response
- Z-transform & Inverse Z-Transform

HW1 Consists of 5 Questions:
- Q1,Q2,Q3: MATLAB Coding Exercises
- Q4: MATLAB AppDesigner
- Q5: MATLAB AppDesigner Bonus Question

Please **Read Submission** and Do all Theoretical and Coding Parts of Exercises and Publish your Work just like The **MATLAB HW-Template** given as Follows and Upload it in [Courses](https://courses.aut.ac.ir/)

Good Luck!

<br>

# MATLAB Coding Exercises
<br>

## Q1. IMPULSE RESPONSE
1. Write a MATLAB program to compute the impulse response of the following systems:

	<img src="https://render.githubusercontent.com/render/math?math=a)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2B0.8y\left(n-1\right)">
   
	<img src="https://render.githubusercontent.com/render/math?math=b)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=x\left(n\ -\ 1\right)%2B0.2y\left(n\ -\ 1\right)%2B0.15y\left(n\ -\ 2\right)%2B1.7x\left(n\ -\ 2\right)">

	<img src="https://render.githubusercontent.com/render/math?math=c)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2B2.3x\left(n-2\right)%2B4x\left(n-4\right)">
   
   
Plot the impulse response h(n) using stem() for n=0,1,…,100. Theoretically, what is the expression for h(n)? Write Down these expressions in your Report. 

2. Of the impulse responses computed in (1), which impulse responses are infinite in duration and which are finite? Which systems are FIR and which systems are IIR? Write Down your Answers and Reasons in your Report.


3. <img src="https://render.githubusercontent.com/render/math?math={\color{Red} Only for 1.b!!!}"><br> Solve the difference equation for y(n), n ≥ 0: driven by the input <img src="https://render.githubusercontent.com/render/math?math=x\left(n\right)=\left(\frac{1}{2}\right)^nu\left[n\right]"> and subject to y(-1) = 0

	a) Plot DTFT magnitude and Phase of y(n) over the interval [-π , π] without Calculation of y(n). (*Hint: Filter Command, fftshift , fft or freqz*)

	b) Determine and Plot y(n) with convolution (*Hint: conv Command*). Plot DTFT magnitude and Phase of y(n).

	c) Plot Frequency Response of y(n)[Y(z) = H(z).X(z)](*Hint: Freqz Command*) and Obtain y(n) from it and plot it. (*Hint: iztrans Command*).

	d) Plot the poles and zeros of H(z), and indicate the ROC.
	
## Q2. RESPONSE OF DISCRETE-TIME SYSTEMS	
	
1. Write a MATLAB program to determine the response of the following system:

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2Bay\left(n-1\right)">
</p>


where a=0.5, and the input signal x(n) is the sinewave, <img src="https://render.githubusercontent.com/render/math?math=x\left(n\right)=3sin\left(2\ \pi\ 0.2n\right)">. Assume zero initial conditions, y(-1)=0.
 Plot y(n), for n=0, 1, 2, …, 100.

2. Repeat (1) for a=0.9, a=1.2, a=-0.5. What happens when a=1.2? Why?

3. Square root algorithm
Most computers and calculators compute the square root of a positive number A using the following recursive algorithm:

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=\frac{1}{2}\left[y\left(n-1\right)%2B\frac{x\left(n\right)}{y\left(n-1\right)}\right]">
</p>

If we use as the input x(n) to this system (algorithm) a step function of amplitude A,
then y(n) will converge after several iterations to the square root of A.
Write a MATLAB program that implements the above algorithm to compute the
square root of: 16, 4, 5 and 3. How many iterations does it take to converge to the true
value assuming y(-1)=0.5? Is the algorithm sensitive to the initial conditions y(-1)?

## Q3. Window
The following finite-duration sequences are called windows and are very useful in DSP. 5 Common windows and their formula, listed below:

### a) Rectangular
<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?R_M%28n%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%201%20%26%20%26%200%5Cleq%20n%3C%20M%5C%5C%200%20%26%20%26%20O.W.%20%5Cend%7Bmatrix%7D%5Cright.">
</p>

MATLAB has `w = rectwin(L)` Command which returns a rectangular window of length L.


```
L = 64;
wvtool(rectwin(L))

```
<p align="center">
  <img src="https://www.mathworks.com/help/examples/signal/win64/RectangularWindowExample_01.png">
</p>
 

<br><br>
### b) Bartlett

<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?B_M%28n%29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20%5Cfrac%7B2n%7D%7BN%7D%20%26%20%26%200%5Cleq%20n%5Cleq%20%5Cfrac%7BN%7D%7B2%7D%5C%5C%20%26%20%26%5C%5C%202%20-%20%5Cfrac%7B2n%7D%7BN%7D%20%26%20%26%20%5Cfrac%7BN%7D%7B2%7D%5Cleq%20n%5Cleq%20N%20%5Cend%7Bmatrix%7D%5Cright.">
</p>

MATLAB has `w = bartlett(L)` Command which returns an L-point symmetric Bartlett window.

```
L = 64;
bw = bartlett(L);
wvtool(bw)

```

<p align="center">
  <img src="https://www.mathworks.com/help/examples/signal/win64/BartlettWindowExample_01.png">
</p>


<br><br>
### c) Hanning
<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?C_M%28n%29%20%3D%200.5%20%5Cbegin%7Bbmatrix%7D%201-%5Ccos%28%5Cfrac%7B2%5Cpi%20n%7D%7BM-1%7D%29%20%5Cend%7Bbmatrix%7DR_M%28n%29">
</p>

MATLAB has `w = hann(L)` Command which returns an L-point symmetric Hann window.

```
L = 64;
wvtool(hann(L))

```

<p align="center">
  <img src="https://www.mathworks.com/help/examples/signal/win64/HannWindowExample_01.png">
</p>

<br><br>
### d) Hamming

<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?H_M%28n%29%20%3D%20%5Cbegin%7Bbmatrix%7D%200.54%20-%200.46%5Ccos%5Cfrac%7B2%5Cpi%20n%7D%7BM-1%7D%20%5Cend%7Bbmatrix%7D%20R_M%28n%29">
</p>

MATLAB has `w = hamming(L)` Command which returns an L-point symmetric Hamming window.

```
L = 64;
wvtool(hamming(L))

```
<p align="center">
  <img src="https://www.mathworks.com/help/examples/signal/win64/HammingWindowExample_01.png">
</p>


### e) BlackMan

<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?BL_M%28n%29%20%3D%20%5Cbegin%7Bbmatrix%7D%200.42%20-%200.5%5Ccos%5Cfrac%7B2%5Cpi%20n%7D%7BM-1%7D%20&plus;%200.08%5Ccos%5Cfrac%7B4%5Cpi%20n%7D%7BM-1%7D%20%5Cend%7Bbmatrix%7D%20R_M%28n%29">
</p>

MATLAB has `w = blackman(L)` Command which returns an L-point symmetric Blackman window.

```
L = 64;
wvtool(blackman(L))

```

<p align="center">
  <img src="https://www.mathworks.com/help/examples/signal/win64/BlackmanWindowExample_01.png">
</p>


for the purpose of this Exercise, For each of these windows, write your own MATLAB function ,determine their DTFTs for M = 10, 50, 101. Scale
transform values so that the maximum value is equal to 1.
Plot the magnitude of the normalized DTFT over −π ≤ ω ≤ π. Study these plots
and comment on their behavior as a function of M and Compare their DTFT's. for instance, the Rectangular Window Function written below:

```javascript
function R = myRect(M)
% Rectangular Window of Length M
	n = 0:M-1;
	R = ones(1,length(n)); 
end
```

### Additional content: 
MATLAB's `Window Designer` ToolBox has All the Comparison Properties of Window Designing. You can Access it by typing `windowDesigner` on Command Window.

<p align="center">
  <img src="https://www.mathworks.com/help/signal/ug/window_blackhamhan.png">
</p>

<br><br>
# MATLAB AppDesigner
<br>

## Q4. APP Designer - Echo
in this exercise, our goal is to add echo to voice signal. for better understanding, please make attention to **Q4 folder** content. the voice signal is in mentioned folder.
the output of echoed signal is obtained from the formula below:

<p align="center">
  <img src="https://latex.codecogs.com/gif.latex?y_%7Becho%7D%5Bn%5D%20%3D%20%5Csum_%7Bk%3D0%7D%5E%7BN%7D%5Calpha%20%5Eky%5Bn-kM%5D">
</p>

we want to study on the effects of parameters N,M and α on output. for this purpose, Develope an App that get an audio signal as input and Gives the echoed signal as output. App must have these features.

- the parameters values must be changeable with **Edit Field** for analysing effects.(initial values are M = 44100, N = 3 and α = 0.7)
- two **buttons** for playing original signal and echoed signal.
- two plots for showing original signal and echoed signal in time domain and frequency domain.(for changing the plot type in time domain and frequency domain, use two **Radio Button**)
- there must be a **Button** to save the echoed signal.
- write down all the results by changing the parameters in your report.
- there is a .wav files in **Q4 folder** which you can test your app.

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/138607623-c3baf2f9-c75d-49f4-95bc-c472de6202f3.png">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/138609889-5584792e-45e2-4479-bcb4-189e5e4216ef.png" width = 500>
</p>


## ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) (Bonus Question) Q5. APP Designer - Pole/Zero Identifier

Design an App according to the clip in **Q5 folder** that Plots the frequency Response of a system by Adding zeros and poles one by one. <br>
Description: for instance, if the system has one zero, z = 1.5 and two poles p = 0.4 + j0.3, 0.4 - j0.3, User must determine the Real part and Imaginary part of a Zero/Pole in **Edit Fields** and then specify the kind of input(Zero or Pole ) by a **Drop Down**. <br>
At last by pushing the **Add Button**, the Zero/Pole is added to system and the frequency response will be updated. by Using a **Radio Button Group** the Different aspect of Frequency Response can be selected.
- Linear Magnitude of Frequency response
- dB Magnitude of Frequency response
- arg Phase of Frequency response
- ARG Phase of Frequency response

Two **Labels** show user, the Number of Zeros and Poles of System.

<p align="center">
  <img src="https://user-images.githubusercontent.com/54024838/138607662-a1fc310b-efd3-4558-8ac2-60a13d84eaf9.png">
</p>




----
**Amirkabir University of Technology, Electrical Engineering Department**
















