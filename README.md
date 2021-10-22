# Dicrete-time Signal Processing - MATLAB HW1
## Dr. Hamid Sheikhzadeh
### DeadLine: 

[__TOC__]

# Introduction
Hi everyone.
MATLAB Homework 1 Test Your Abilities for Following Content:
- Convolution
- Impulse Respones
- Frequency Response
- Z-transform & Inverse Z-Transform

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

