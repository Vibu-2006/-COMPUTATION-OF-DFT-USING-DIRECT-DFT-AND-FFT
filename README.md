
# EXP 2 : COMPUTATION OF DFT USING DIRECT DFT AND FFT

# AIM: 
  To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
## DISCRETE FOURIER TRANSFORM:

```
clc; 
clear; 
xn=[1 2 3 4 3 2 1]; 
 
n1=0:1:length(xn)-1; 
subplot(3,1,1); 
plot2d3(n1,xn); 

xlabel('Time n'); 
ylabel('Amplitude xn'); 
title('Input Sequence'); 

j=sqrt(-1); 
N=length(xn); 
Xk=zeros(1,N); 
for k=0:N-1 
for n=0:N-1 
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N); 
end 
end 
disp(Xk) 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(3,1,2); 
plot2d3(K1,magnitude); 

xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 

angle = atan(imag(Xk),real(Xk)) 
subplot(3,1,3); 
plot2d3(K1,angle); 

xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum'); 

```

### CALCULATIONS: 


![Uploading image.png…]()


### SAMPLE OUTPUT: 

<img width="1916" height="1190" alt="Screenshot 2026-02-23 093317" src="https://github.com/user-attachments/assets/1b4691aa-ee5c-4637-aed5-e1a41ae6d698" />

## FAST FOURIER TRANSFORM:

```
clear; 
clc; 
close; 
xn = [1 2 3 4 3 2 1] 
 
n1=0:1:length(xn)-1; 
subplot(2,2,1); 
plot2d3(n1,xn); 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
10 
 
Xk = fft(xn); 
 
K1=0:1:length(Xk)-1; 
magnitude=abs(Xk) 
subplot(2,2,2); 
plot2d3(K1,magnitude); 
xlabel('frequency(Hz)'); 
ylabel('magnitude(gain)'); 
title('magnitude spectrum'); 
angle = atan(imag(Xk),real(Xk)) 
subplot(2,2,3); 
plot2d3(K1,angle); 
xlabel('frequency(Hz)'); 
ylabel('Phase'); 
title('Phase spectrum') 
y= ifft(Xk) 
 
n2=0:1:length(y)-1; 
subplot(2,2,4) 
plot2d3(n2,y) 
xlabel('Time n'); 
ylabel('Amplitude'); 
title('Inverse FFT OF X(K)');

```
### CALCULATIONS: 

![20260224_204752](https://github.com/user-attachments/assets/51a45195-0bd3-4bcf-bd39-f51293c15192)
![20260224_204756](https://github.com/user-attachments/assets/9d2b5a50-ada8-4073-bfc8-b015e3480db1)
![20260224_204803](https://github.com/user-attachments/assets/1be90cb6-dcc8-469b-934f-2fd166b62ff0)

### SAMPLE OUTPUT: 

<img width="1919" height="1199" alt="Screenshot 2026-02-23 093422" src="https://github.com/user-attachments/assets/08ba66da-6aae-478d-8317-2b0882ddd6b6" />

# RESULT: 
