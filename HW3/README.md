<div align="center">
<i>In The Name Of God</i>

<p>
  <img src="https://user-images.githubusercontent.com/47852354/138564509-b5dffb4e-f48b-4db5-b8a4-1385ef2b22c8.png" width="200">
</p>

# Dicrete-time Signal Processing - MATLAB HW3
### Deadline: Friday, 2021 Dec.10 - 23:59 (GMT+3:30)
---
**Dr. Hamid Sheikhzadeh - TAs: Arshia Samoudi - Saleh Tabatabaei**
</div>

# Introduction
Hi everyone.

HW3 Consists of 4 Questions:
- Q1,Q2 : Chapter 7 (FIR and IIR Filter Designing)
- Q3,Q4 : Chapter 8 (DFT , DFS)

Q1,Q2 Tests Your Abilities in Following Content:
- Designing FIR and IIR filters

Please **Read Submission** and Do all Theoretical and Coding Parts of Exercises and Publish your Work just like The **MATLAB HW-Template** given as Follows and Upload it in [Courses](https://courses.aut.ac.ir/)

Good Luck!


<br>

# MATLAB Coding Exercises
<br>

## Q1. FIR Filter Design

for this questions, it's better to study the **Table 7.2 of Discrete-time Signal Processing** and **section 7.3(Window Design Techniques) from Digital Signal Processing using MATLAB**

### A. Windowing
1. Design Digital FIR Filter with the following desirable specifications:

  <p align="Center">
    <img src="https://user-images.githubusercontent.com/54024838/145671537-e338fc4a-2998-4815-9417-2280ebdd47b4.png" width="550" >
  </p>

- According to Table 7.2 of the Oppenheim and preferred As, select the appropriate window type and then using MATLAB to 
Find the corresponding value.

- Design the required ideal filter using the ideal_lp command; Also with determined parameters
In the previous section, design the window using MATLAB commands, finally by using the windowing technique, get the filter impulse response

- Plot ideal filter impulse response, window impulse response, determined filter impulse response and frequency response (Magnitude). (You can use the freqz_m command). Obtain The final value of Rp and As of the designed filter and explain it in your work report.

### B. Kaiser
2. Using the following equations, repeat the previous steps this time to design the appropriate filter using the Kaiser window.
(Draw the filter diagrams as in the previous section and note the β and M values obtained in the work report. Explain your design).

  <p align="Center">
    <img src="https://user-images.githubusercontent.com/54024838/145674102-09430d7f-f9d2-4c9b-868a-eb33e68791b3.png" width="450" >
  </p>

### C. Filtering
3. There is an audio file attached to Question 1 that covers different frequencies. Read this audio file. Draw its frequency response. Put Two filters designed in parts (a) and (b) on the audio signal and draw the output frequency response.

4. What were the differences if we used a rectangular window for design?


## Q2. IIR Filter Design

for this questions, it's better to study the **section 8.4** and **section 8.5 from Digital Signal Processing using MATLAB**

### A. Bilinear transformation
1. Design a digital IIR filter with the following specifications (consider the value of T as 2 where necessary)

  <p align="Center">
    <img src="https://user-images.githubusercontent.com/54024838/145674331-f8bb27e5-445a-4f57-a776-6715d4c504b2.png" width="450" >
  </p>

The desired filter using the design method of Butterworth analog filter and two-line conversion (Bilinear transformation) 
Follow the steps below.

- First find Ωp and Ωs of analog frequencies according to the corresponding relations.
- Use the afd_butt command and find the corresponding analog filter coefficients. Specify the order of the N-Butterworth Filter.
- In your work report write the relationships related to two-line conversion to convert analog filter to digital, analog filter to
Convert the result obtained in the previous step to a digital filter using the bilinear command in MATLAB.
- Plot Magnitude and phase of the digital filter frequency response; Explain in your work report and write down H(z).

### B. Normalized Butterworth
2. Design the filter of part (a) this time using another method in MATLAB during the following steps:

- First find Ωp and Ωs of analog frequencies according to the corresponding relations
- Write the relations related to the Butterworth filter at the frequencies Ωp and Ωs and use it as a relation to find the N(Filter Order). Using this relation in MATLAB, calculate N and Ωc and write in your work report
- Find ωn using the following equation. (π in the denominator of the relation is not because of the two-line conversion but because
In MATLAB, all frequencies are on the scale of π

  <p align="Center">
    <img src="https://user-images.githubusercontent.com/54024838/145674649-6b07566a-6589-4aeb-8aa6-9544cb9d0015.png" width="200" >
  </p>

- Use the butter command to find the corresponding digital filter and plot the size and phase of the digital filter frequency response.
Explain in your work report and write down H(z)

### C. Filtering
3. There is an audio file attached to Question 2 that covers different frequencies. Read this audio file. Draw its frequency response. Put Two filters designed in parts (a) and (b) on the audio signal and draw the output frequency response.

4. As you know, to design an IIR filter, we can use other analog filters besides the Butterworth filter.
For example, elliptic, Chebyshev-I, and .Chebyshev-II. Investigate these filters briefly.
Explain in your report. Which of these filters is best for design?


## Q3. Convolution and DFT
for this questions, it's better to study the **section 8.7 from Discrete-Time Signal Processing Book**

### A. cflip
1. Write a function called cflip in MATLAB that has two inputs. **sig[n]** (a signal) and **n** (an integer) And give modulo N at the output of the signal sig[-n modulo N].

``` java script
    function cflipped_sig = cflip(sig, N)
    ...
    end
```

### B. cshift
2. Write a function called cshift in MATLAB that has two inputs. **sig[n]** (a signal) and **m** (an integer) And Calculate the circular shifted with the order m at the output.

``` java script
    function cshifted_sig = cshift(sig, m)
    ...
    end
```

### C. Circular Convolution
3. Using the functions of parts (a) and (b), write a MATLAB function to calculate the circular convolution of two signals with N(integer).

``` java script
    function output_sig = cconv(sig1, sig2, N)
    ...
    end
```

### D. DFT Properties
4. As we know from the properties of DFT, the circular convolution of two signals in the time domain is matched with the product of Their DFTs in the frequency domain.

  <p align="Center">
    <img src="https://user-images.githubusercontent.com/54024838/147384567-9c827f47-0ab7-4ee3-8a50-ecf844d4d4af.png" width="300" >
  </p>

Calculate Circular convolution both pairs of the following signals using both methods and Then complete the results. Compare the output obtained from the two methods and explain it in your work report.

**1st Signal pair : Rectangular pulses with lengths 4, 8 which start at n = 4, N = 21**

**2nd Signal pair : Rectangular pulses with lengths 7, 11 which start at n = 5, N = 21**

- Method1: Using the cconv function written in part (c)
- Method2: Calculation of DFT of each of the two time signals, calculation of the product of frequency multiplication then use IDFT (Reverse DFT) (Use the fft, ifft commands to calculate DFT, IDFT)

5. For which pair circular convolution and linear convolution are the same? and what is the reason? Explain in your work report


----
**Amirkabir University of Technology, Electrical Engineering Department**

















