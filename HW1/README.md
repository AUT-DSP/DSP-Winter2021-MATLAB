*In The Name Of God*
# Dicrete-time Signal Processing - MATLAB HW1
### Deadline: Friday, 2021 Nov.5 - 23:59 (GMT+3:30)
---
**Dr. Hamid Sheikhzadeh - TAs: Arshia Samoudi - Saleh Tabatabaei**


# Introduction
Hi everyone.
MATLAB Homework 1 Tests Your Abilities in Following Content:
- Convolution
- Impulse Respones
- Frequency Response
- Z-transform & Inverse Z-Transform

HW1 Consists of 4 Parts:
- Parts A,B & C: MATLAB Coding Exercises
- Part D: MATLAB AppDesigner

Please **Read Submission** and Do all Theoretical and Coding Parts of Exercises and Publish your Work just like The **MATLAB HW-Template** given as Follows and Upload it in [Courses](https://courses.aut.ac.ir/)

Good Luck!

## 1.CONVOLUTION
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

## 2. IMPULSE RESPONSE
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
	
## 3. RESPONSE OF DISCRETE-TIME SYSTEMS	
	
1. Write a MATLAB program to determine the response of the following system:

<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=y\left(n\right)=4.5x\left(n\right)%2Bay\left(n-1\right)">
</p>



where a=0.5, and the input signal x(n) is the sinewave, <img src="https://render.githubusercontent.com/render/math?math=x\left(n\right)=3sin\left(2\ \pi\ 0.2n\right)">. Assume zero initial conditions, y(-1)=0.
 Plot y(n), for n=1, 2, …, 100.

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


----
**Amirkabir University of Technology, Electrical Engineering Department**















