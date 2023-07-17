# bernstein_vazirani

An implementation of the Bernstein-Vazirani quantum algorithm.
- The 1st section uses for n=4 qubits with the secret string 1011
- The second section is applicable to any secret string of any length
***
The Bernstein-Vazirani algorithm is an example of a quantum algorithm that outperforms classical methods.
- Let's say you have a secret string of 1's and 0's. Then put the secret string in a box (function).
- Now the computer wants to determine what's inside the box by guessing the secret number.

Classically, 
- the comp can apply AND operations by guessing n attempts
- or exponentially: for n-bit secretNum, tries from 0 to 2^n-1

Using Bernstein-Vazirani's alg
- finds secretNum in 1 attempt (regardless of secretNum size)

reference: https://github.com/qiskit-community/qiskit-community-tutorials/blob/master/Coding_With_Qiskit/ep6_Bernstein-Vazirani_Algorithm.ipynb

***
## Algorithm

1. initialize 1st n qubits in |0> state, & last qubit in |1> state
2. apply Hadamard gates to all qubits
3. build oracle (box containing secret number)
4. measure the 1st n qubits in the Bell basis (applying h gates before measurements)
***

## Section 1
n=4 qubits, secret string: 1011

<img width="947" alt="Screenshot 2023-07-17 at 5 05 39 PM" src="https://github.com/jaszmine/bernstein_vazirani/assets/52623824/789c100e-d150-4455-b7e9-443d45b5f716">

output: {'1011': 1}

## Section 2
n=11 qubits, secret string: 10111100101

<img width="867" alt="Screenshot 2023-07-17 at 5 08 21 PM" src="https://github.com/jaszmine/bernstein_vazirani/assets/52623824/c6fda9c9-da3d-46f9-ba2e-9eefd012cc1a">

<br>
<br>
The histogram shows how 100% of the results contain the secret number (this example uses 1 shot).
<img width="514" alt="Screenshot 2023-07-17 at 5 09 19 PM" src="https://github.com/jaszmine/bernstein_vazirani/assets/52623824/cafbd288-1b23-4aae-86de-e1206389fb6f">

output: {'10111100101': 1}

