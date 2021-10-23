# Dicrete-time Signal Processing - MATLAB HW1
## Dr. Hamid Sheikhzadeh
### DeadLine: 

[__TOC__]

# Introduction
Hi everyone.
MATLAB Homework 1 Tests Your Abilities for Following Content:
- Convolution
- Impulse Respones
- Frequency Response
- Z-transform & Inverse Z-Transform

HW Contains 3 Parts(A,B & C). Please Do all Theoretical and Coding Parts of Exercises and Publish your Work just like The **Template** given as Follows.

Good Luck!

## A.CONVOLUTION
1. Write a MATLAB program that implements the convolution sum:

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=\sum_{k=-\infty}^{\infty}x\left(k\right)h\left(n-k\right)">
</p>

for arbitrary input signal x(n) and impulse response h(n). Implement the convolution as a function of the form: y=convol(x,h). The function should take as input 		arguments the signal vector x(n), and impulse response h(n), and should return the output in the vector y. Assume that the signals x(n), and h(n) are zero for n<0.


2. Using the convolution program developed in (1), convolve the following sequences:


a)<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=x_1\left(n\right)=\left[1,1,1,1,1\right]">
</p>

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=x_2\left(n\right)=\left[1,1,1,1,1,1,1\right]">
</p>

b)<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=x_1\left(n\right)={0.5}^n">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=0\le n\le100">
</p>

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=x_2\left(n\right)={0.9}^n">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=0\le n\le100">
</p>

## B. IMPULSE RESPONSE
1. Write a MATLAB program to compute the impulse response of the following systems:

	<img src="https://render.githubusercontent.com/render/math?math=a)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2B0.8y\left(n-1\right)">
   
	<img src="https://render.githubusercontent.com/render/math?math=b)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=x\left(n\ -\ 1\right)%2B0.2y\left(n\ -\ 1\right)%2B0.15y\left(n\ -\ 2\right)%2B1.7x\left(n\ -\ 2\right)">

	<img src="https://render.githubusercontent.com/render/math?math=c)">&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2B2.3x\left(n-2\right)%2B4x\left(n-4\right)">
   
   
Plot the impulse response h(n) using stem(). Theoretically, what is the expression for h(n)? Plot the impulse response h(n), for n=0,1,…,100.

2. Of the impulse responses computed in (1), which impulse responses are infinite in
duration and which are finite? Which systems are FIR and which systems are IIR?




3. <img src="https://render.githubusercontent.com/render/math?math={\color{Red} Only for B1.b!!!}"><br> Solve the difference equation for y(n), n ≥ 0: driven by the input <img src="https://render.githubusercontent.com/render/math?math=x\left(n\right)=\left(\frac{1}{2}\right)^nu\left[n\right]"> and subject to y(-1) = 0

	a) Plot DTFT magnitude and Phase of y(n) over the interval [-π , π] without Calculation of y(n). (Hint: Filter Command, fftshift , fft)

	b) Determine and Plot y(n) with convolution (Use the convol Function From A.1). Plot DTFT magnitude and Phase of y(n).

	c) Plot Frequency Response of y(n) (Hint: Freqz Command) and Obtain y(n) from it and plot it. (Hint: iztrans Command).

	d) Plot the poles and zeros of H(z), and indicate the ROC.

