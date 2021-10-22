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

```math
a^2+b^2=c^2
```

$'y\left(n\right)=\sum_{k=-\infty}^{\infty}x\left(k\right)h\left(n-k\right)'$

for arbitrary input signal x(n) and impulse response h(n). Implement the convolution as a function of the form: y=convol(x,h). The function should take as input arguments the signal vector x(n), and impulse response h(n), and should return the output in the vector y. Assume that the signals x(n), and h(n) are zero for n<0.

2. Using the convolution program developed in (1), convolve the following sequences:

	x_1\left(n\right)=\left[1,1,1,1,1\right]
x_2\left(n\right)=\left[1,1,1,1,1,1,1\right]


	x_1\left(n\right)={0.5}^n				0\le n\le100
x_2\left(n\right)={0.9}^n				0\le n\le100
