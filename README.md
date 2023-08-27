# QuantumFullAdder
Implementing Full Adder using QISKIT and IBMQ infrastructure for computation

# Introduction / Roy Ben Avraham, 27/08/2023

In this repo you will see how to implement the quantum equivalent of a Full Adder on IBMs quantum computers using quantum logic gates. 
What is a Full Adder? 
A Full Adder is a logic circuit used by classical computers to implement addition on up to 3 bits. 

The Full Adder circuit contains 3 inputs: A, B, and Cin (short for Carry in.as it carries in from the previous Full Adder since they can be stringed together)

There are also 2 outputs called Sum and Cout (Short for carry out as it carries out a bit to the Cin of the next adder)


# Implementation
To implement a Full Adder on a quantum computer we will need 4 qubits (ie 1 for each input and output of the Full Adder). 

Q0: Qubit for input A 

Q1: Qubit for Input B 

Q2: Qubit for Input Cin 

Q3: Qubit for Sum 

Q4: Qubit for Cout 



# How it works

For calculating the Sum we simply apply a CNOT gate to Q3 (Sum) from all inputs. This means that if any one of the inputs are 1 then Q3 will be flipped to 1. If all inputs are 0 then Q3 will remain 0. 

To calculate Cout (Q4) we apply Toffoli gates with Q4 as the target and the input combinations (Q0,Q1), (Q0,Q2), (Q1,Q2) as the control qubits. 

Note: Because of the order of the gates we can never get the Sum and Cout to both equal 1 if only 2 of the inputs are 1. 
