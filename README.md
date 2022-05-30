# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs

### HARDWARE REQUIRED:  
– PC, Cyclone II , USB flasher

### SOFTWARE REQUIRED:  
Quartus prime

### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
1. Start the module using module projname().
2. Declare the inputs and outputs along with the select lines according to the multiplexer and      demultiplexer.
3. Use wire to assign intermediate outputs.
4. Use and,or and not gates to get the desired output.
5. End the module.
6. Generate RTL realization and timing diagrams

### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: Lakshmi priya
RegisterNumber:  212221230053
```
## 4X1 MULTIPLEXER:
```
module mux(I0,I1,I2,I3,S0,S1,Y);
input I0,I1,I2,I3,S0,S1;
output Y;
wire S0C,S1C;
not(S0C,S0);
not(S1C,S1);
wire P,Q,R,S;
and(P,S0C,S1C,I0);
and(Q,S0C,S1,I1);
and(R,S0,S1C,I2);
and(S,S0,S1,I3);
or(Y,P,Q,R,S);
endmodule
```
### RTL LOGIC  
![170941003-4096d9f6-a553-4b38-83fe-185a30a08d0a](https://user-images.githubusercontent.com/93427923/170995892-116aa6c7-959e-4509-b60b-5f94c8dd6ff2.png)

### TIMING DIGRAMS  
![170946737-be2b2a24-338d-49d5-8f46-d84e4cb7fd6a](https://user-images.githubusercontent.com/93427923/170995899-62b49a07-694f-43f3-82e9-2e1923978bd5.png)
![170946752-39f79526-a86c-4085-97b1-920106a4f6a1](https://user-images.githubusercontent.com/93427923/170995922-2c203082-2c3a-411c-924d-340469ee21a7.png)
![170946795-b8c2ddb0-2e3f-45c6-ad47-28997b8bfe0f](https://user-images.githubusercontent.com/93427923/170995939-f87d6437-1283-4108-9b26-5a9b0d703554.png)
![170946822-85b7650e-02cc-4be8-ab59-516da6cbc528](https://user-images.githubusercontent.com/93427923/170995963-4f5f11ee-845b-4a7c-9fb2-1565e9c17c93.png)

### TRUTH TABLE 
![170941232-ca344308-cd3e-4d7b-89b2-ea0c263f5fe1](https://user-images.githubusercontent.com/93427923/170995978-daf75e4b-f551-4560-8df8-0da57f107c4b.png)

## 1X4 DEMULTIPLEXER:
```
module demux(I,S0,S1,Y0,Y1,Y2,Y3);
input I,S0,S1;
output Y0,Y1,Y2,Y3;
wire S0C,S1C;
not(S0C,S0);
not(S1C,S1);
and(Y0,I,S0C,S1C);
and(Y1,I,S0C,S1);
and(Y2,I,S0,S1C);
and(Y3,I,S0,S1);
endmodule
```
### RTL LOGIC
![170941394-06d8504a-4516-4281-aa2d-51967e8a995d](https://user-images.githubusercontent.com/93427923/170996159-bee0a54c-fa26-4c35-b71f-62312fec7b8f.png)

### TIMING DIGRAMS
![170941435-9fc58d3e-a1a0-4d83-8175-9597e4be8bf1](https://user-images.githubusercontent.com/93427923/170996180-94c17a0e-df18-48a8-bed0-452dc6e12815.png)

### TRUTH TABLE
![170941466-d2d32783-7b8f-4b13-88b6-fff20dcb9e13](https://user-images.githubusercontent.com/93427923/170996228-f720dece-07e2-450d-8dec-3b755f738bf0.png)

### RESULTS
Hence 4x1 Multiplexer and 1x4 Demultiplexer is been implemented and verified using verilog programming and its output are validated.
