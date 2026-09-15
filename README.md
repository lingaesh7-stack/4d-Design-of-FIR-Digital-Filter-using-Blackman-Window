# FIR-FILTER-DESIGN
# EXP 4 d: Design-of-FIR-Digital-Filter-using-Blackman-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Blackman-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = wc / %pi;
    else
        hd(n+1) = sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/68bb6daa-52a2-4e2c-9fc3-a0f5719c09cb" />

# RESULT: 

Thus design of low pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc = %pi / 2;         
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - (wc / %pi);
    else
        hd(n+1) = -sin(wc * (n - alpha)) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="893" alt="image" src="https://github.com/user-attachments/assets/ffdb376c-a048-4a3c-b573-fd70cb085e5e" />

# RESULT: 
Thus design of HIGH pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = (wc2 - wc1) / %pi;
    else
        hd(n+1) = (sin(wc2 * (n - alpha)) - sin(wc1 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/7c322308-cc01-416e-89f0-b3db858ddcc4" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc;
clear;
close;

N = 21;               
wc1 = %pi / 4;        
wc2 = 3 * %pi / 4;    
alpha = (N - 1) / 2;  

hd = zeros(1, N);
for n = 0 : N-1
    if n == alpha then
        hd(n+1) = 1 - ((wc2 - wc1) / %pi);
    else
        hd(n+1) = (sin(wc1 * (n - alpha)) - sin(wc2 * (n - alpha))) / (%pi * (n - alpha));
    end
end

w = zeros(1, N);
for n = 0 : N-1
    w(n+1) = 0.42 - 0.5 * cos((2 * %pi * n) / (N - 1)) + 0.08 * cos((4 * %pi * n) / (N - 1));
end

h = hd .* w;         

[H, w_freq] = frmag(h, 256); 

figure;
subplot(2, 1, 1);
plot2d3(0:N-1, h);          
plot(0:N-1, h, 'ro');       
xtitle('Impulse Response', 'n', 'h(n)');
xgrid(1);

subplot(2, 1, 2);
H_dB = 20 * log10(H);       
plot(w_freq, H_dB);
xtitle('Magnitude Response', 'Normalized Frequency', 'Magnitude (dB)');
xgrid(1);
```

# OUTPUT: 

<img width="1917" height="896" alt="image" src="https://github.com/user-attachments/assets/4d9a803c-a9eb-42fe-bc02-2ccaf5797782" />

# RESULT: 
Thus design of BAND STOP FIR digital filter using-Blackman-Window waveforms were plotted and output was verified.
