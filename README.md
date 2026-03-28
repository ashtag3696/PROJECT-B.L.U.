<p align='center'>PROJECT : B.L.U.</p>
<p align='center'>Binary	Logical	Unit</p>



<p align='center'>Design and Simulation of a 4-Function, 2-Bit ALU (Arithmetic Logical Unit)</p>



Software used : Digital (Github : hneemann/Digital)


Contributors:

[@beppvis](https://github.com/beppvis) &nbsp; [@ashtag](https://github.com/ashtag3696)
<br>
<br>
 
Objective:

The aim of this project is to familiarize students with the design, simulation, and analysis of digital circuits using simulation tools such as Multisim, Tinkercad Circuits, Logisim, or any other preferred simulation software. Students will explore different digital electronics concepts, simulate the circuits, and analyze their behavior.

<br>
1.	Introduction

The Arithmetic Logic Unit (ALU) is a critical digital circuit that serves as the computational core of a CPU. The objective of this project is to design, simulate, and analyze a 4-bit ALU capable of performing four fundamental arithmetic operations: Addition, Multiplication, and Division. This case study documents the design process, from the logical foundation of each operation to its implementation and verification in the "Digital" simulation software. The project demonstrates a practical application of key digital electronics concepts, including combinational logic, Boolean algebra, and modular circuit design.



<br>
2.	Circuit Design and Explanation

The ALU is designed to accept two 4-bit binary inputs (A and B) and a 2-bit opcode to select one of the four operations. The output is a binary number which is then decoded and displayed in a human-readable decimal format.


Block Diagram
<img width="1025" height="878" alt="image" src="https://github.com/user-attachments/assets/371c0e41-5b75-49d8-b0f5-07700d996ec6" />

 
Inputs:

A[1:0]: A 4-bit binary operand.

B[1:0]: A 4-bit binary operand.

S[1:0]: A 2-bit opcode to select the function (00: Multiply, 01:Divide, 10: Add).


Functional Units:

Addition: 
Implemented using a standard 4-bit full adder circuit, which sums the bits of A and B and handles the carry between stages.


Multiplication: 
Implemented as a 2-bit by 2-bit combinational array multiplier. The circuit uses AND gates to generate partial products, which are then summed using a network of adders to produce the final 4-bit product.


Division (Floor): 
Implemented as a combinational divider. This was designed by first creating a complete truth table for all possible 4-bit dividend and 2-bit divisor inputs. The logic equations for each output bit of the quotient were then derived and simplified using Karnaugh Maps. The resulting complex Boolean expressions were built directly from basic AND, OR, and NOT gates.


Output and Display: 
A 4-to-1 multiplexer selects the output from the appropriate functional unit based on the opcode. This result is then sent to 7447 BCD-to-7-segment decoders to be displayed on Seven-Seg display units.

<br>
3.	Simulation Results

The circuit's functionality was verified for all four operations using the "Digital" simulator.


a)	Addition (Opcode 10): 3+ 2 = 5

Screenshot showing inputs A=11, B=10, Opcode=10, and the display showing '5'.
<img width="1031" height="914" alt="image" src="https://github.com/user-attachments/assets/3be35c13-c81b-4bcd-8f38-a44c442e63a9" />


 
b)	Multiplication (Opcode 00): 3 x 3 = 9

Screenshot showing inputs A=11, B=11, Opcode=00, and the display showing '9'.
<img width="1019" height="928" alt="image" src="https://github.com/user-attachments/assets/b7809fc7-d9bb-479d-9eaa-edb19037a1d8" />



 
c)	Division- Floor (Opcode 01): 2 / 3 = > Quotient =0, Remainder=2

Screenshot showing inputs A=10, B=11, Opcode=01, and the display showing '0' (Quotient) and ‘2’ (Remainder)
<img width="1036" height="952" alt="image" src="https://github.com/user-attachments/assets/dfcefd4b-7873-4fa2-b0af-e24b6696784b" />



 <br>
4.	Analysis and Discussion

The behavior of the circuit and its logical operations were analyzed, and the outputs were confirmed to be correct.

Division: 
The combinational divider works instantly for any given input, as it is a pure logic circuit. However, this approach has a significant trade-off: the number of gates required is immense and scales exponentially with the number of input bits. While effective for small numbers, this method is impractical for larger ALUs (e.g., 32-bit or 64-bit), where sequential algorithms are used instead.

Limitations:

1.	Subtraction was not possible due to bit limt (current bits=2)





<br>
5.	Challenges Faced

Several challenges were encountered during the design and simulation of the ALU.


a) Designing the Combinational Divider: 
This was the most labor-intensive part of the project. Creating a full truth table, accurately simplifying the logic for each output bit with K-maps, and then translating those complex equations into a large, intricate circuit was a major challenge that required meticulous attention to detail.


b) Circuit Complexity and Wiring: 
As the number of functions grew, managing the routing of data and control signals became increasingly difficult. Keeping the schematic organized to prevent wiring errors was a constant challenge.




<br>
6.	Conclusion

 
This project successfully achieved the goal of designing, simulating, and analyzing a 4-bit, 4-function ALU. The final circuit correctly performs addition, multiplication, and division. The process provided valuable insight into the design of core CPU components, the practical application of Boolean algebra and K-maps, and the trade-offs between different implementation strategies, such as the combinational divider.


Future improvements could include zero, and negative conditions; expanding the design to 8 bits; and adding logical operations (AND, OR, XOR) and adding Subtraction function to make it a more complete ALU.
