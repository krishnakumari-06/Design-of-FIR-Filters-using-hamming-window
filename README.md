# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF HIGH PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM :
~~~
 
 clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = 1 - (Wc/%pi);
    else
        hd(n) = -sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Hamming Window
for n = 1:M
    W(n) = 0.54 - 0.46*cos((2*%pi*(n-1))/(M-1));
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hamming Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hamming Window');

~~~


# OUTPUT :
 <img width="405" height="433" alt="image" src="https://github.com/user-attachments/assets/97096daa-cca7-4fa6-9fa6-de423e55dd41" />



# RESULT :
Thus, the High Pass FIR Digital Filter was successfully designed and implemented using the Hamming Window method in SCILAB. The impulse and magnitude responses were obtained and verified.


