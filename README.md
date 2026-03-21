# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM :
~~~
clear;
close;

N = 51;                      
fc = 0.4;                    
n = 0:N-1;
alpha = (N-1)/2;

// Ideal High Pass Filter Impulse Response
hd = -sin(2*%pi*fc*(n - alpha)) ./ (n - alpha);
hd(alpha+1) = 1 - 2*fc;      

w = 0.54 - 0.46*cos(2*%pi*n/(N-1));
h = hd .* w;
// Plot Impulse Response
subplot(2,1,1);
plot(n, h, 'r');
xlabel('n');
ylabel('h(n)');
title('Impulse Response of FIR High Pass Filter using Hamming Window');
grid on;

[H, f] = frmag(h, 512);     
subplot(2,1,2);
plot(f, abs(H));
xlabel('Normalized Frequency');
ylabel('|H(f)|');
title('Magnitude Response of FIR High Pass Filter');
grid on;
~~~


# OUTPUT :
<img width="926" height="573" alt="image" src="https://github.com/user-attachments/assets/4d5a286d-f98e-427e-9296-724fab590315" />


# RESULT :
Thus, the High Pass FIR Digital Filter was successfully designed and implemented using the Hamming Window method in SCILAB. The impulse and magnitude responses were obtained and verified.


