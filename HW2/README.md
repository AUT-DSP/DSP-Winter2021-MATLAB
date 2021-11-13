<div align="center">
<i>In The Name Of God</i>

<p>
  <img src="https://user-images.githubusercontent.com/47852354/138564509-b5dffb4e-f48b-4db5-b8a4-1385ef2b22c8.png" width="200">
</p>

# Dicrete-time Signal Processing - MATLAB HW2
### Deadline: Friday, 2021 Nov.8 - 23:59 (GMT+3:30)
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
1. Write a MATLAB program to compute Reconstructed Signals Obtained From sinc interpolation

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



----
**Amirkabir University of Technology, Electrical Engineering Department**
















