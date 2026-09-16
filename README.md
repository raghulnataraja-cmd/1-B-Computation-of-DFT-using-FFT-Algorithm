# EXPT 1b: Computation-of-DFT-using-FFT-ALGORITHM

## AIM
To perform and verify DFT using FFT-ALGORITHM by SCILAB.
## APPARATUS REQUIRED
PC installed with SCILAB
## PROGRAM 
### DFT FFT-ALGORITHM
```
clear;
clc;

// 1. Define Input Sequence
x = [1, 2, 3, 4, 4, 3, 2, 1];
N = length(x);
n = 0:(N-1);
k = 0:(N-1);

disp("Original Sequence x(n):");
disp(x);

// 2. Compute DFT using built-in FFT
Xk = fft(x);
mag = abs(Xk);
phase = atan(imag(Xk), real(Xk));

disp("Computed FFT values X(k):");
disp(Xk);

// 3. Compute Inverse FFT
y = ifft(Xk);

// --- Plotting Setup ---
figure(1);
clf(); // Clear current figure window
bg_grid = color("lightgrey"); // Soft background grid

// Subplot 1: Input Sequence
subplot(2, 2, 1);
plot2d3(n, x, style=2); 
plot(n, x, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Input Sequence', 'Time (n)', 'Amplitude x(n)');
xgrid(bg_grid);

// Subplot 2: Magnitude Spectrum
subplot(2, 2, 2);
plot2d3(k, mag, style=2);
plot(k, mag, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Magnitude Spectrum', 'Frequency Index (k)', 'Magnitude |X(k)|');
xgrid(bg_grid);

// Subplot 3: Phase Spectrum
subplot(2, 2, 3);
plot2d3(k, phase, style=2);
plot(k, phase, 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Phase Spectrum', 'Frequency Index (k)', 'Phase (radians)');
xgrid(bg_grid);

// Subplot 4: Reconstructed Sequence (Inverse FFT)
subplot(2, 2, 4);
plot2d3(n, real(y), style=2);
plot(n, real(y), 'ro', "MarkerFaceColor", "red", "MarkerSize", 6);
xtitle('Inverse FFT (Reconstructed)', 'Time (n)', 'Amplitude y(n)');
xgrid(bg_grid);
```

### SAMPLE OUTPUT:

<img width="1536" height="704" alt="image" src="https://github.com/user-attachments/assets/5792ad72-fe26-47e1-a39e-6a5788445709" />

## RESULT:
Thus,  DFT using FFT-ALGORITHM for two given sequences were performed and its result was verified.

