---
progress: "0"
tags:
  - quantum-computing-fundamentals
---

[[Introduction to Quantum Computing (Wong).pdf]]

---

# Introduction to Quantum Computing (Hiu Yung Wong)

- Unitary
	- Every operation must be unitary
	- Implies reversibility of operations
	- Determinant of 1
	- Every quantum gate can also be viewed as a rotation operator
	- Hence, if an operator can rotate in one direction, then clearly it can in the reverse
	- Also implies that the inner product of two vectors (overlap of two wavefunctions) is preserved after a unitary operator is applied to them both
- Low temperature is required since the energy separation between basis states is typically very small such that we need low temperature to eliminate thermal population (or noise) accordiing to the Boltzmann distribution
- No cloning theory
	- Some states can be cloned
	- Some states cannot be cloned
	- Measurement of a superposition state results in its collapse into the constituent basis states. ie information is destroyed during measurement
- Qbit implementation
	- Needs to be small in order to obey quantum mechanical laws (cf correspondence principle)
	- Needs to distinguishable basis states
- Information size
	- We can store $2^n$ states with $n$ cbits, for instance with 2 bits we get four states
		- 00, 01, 10, 11
	- With $n$ qubits, each possible classical state becomes a quantum basis state (each being orthogonal)
	- Thus for $n$ qubits we get $2^n$ basis states and each of these can form superpositions to yield infinitely many quantum states
- Quantum parallelism
	- If you have 100 qubits, you can form a system of $2^{100}$ basis vectors.
	- This is more than the number of atoms in the universe.
	- If you can process the 100 qubits at the same time (all you need is just a 100-qubit gate), you are processing the 2100 coefficients at once.
- Inner product
	- Always yields a scalar
	- Corresponds to overlap of one vector onto another or its projection
	- Gram–Schmidt process is a method for orthonormalizing a set of vectors in an inner product space
- Dual space
	- The set of vectors in bra space form the dual space of the set of vectors in ket space
- Copenhagen interpretation
	- Born interpretation
	- Measuring a superposition results in its collapse and is irreversible
	- Square of coefficient corresponds to probability of measuring given state in superposition
- Choosing basis states
	- We see that every measurement corresponds to an observable and each measure- ment result must be a basis state corresponding to that observable/measurement.
	- Therefore, it is very normal to choose the possible measurement results to form the basis states
	- In summary, _a basis formed by the basis states corresponding to an observable is a convenient choice in the formulation of the quantum computing problems._
- Formalisms of quantum mechanics
	- Wave quantum mechanics (Schrödinger) and matrix quantum mechanics (Heisenberg)
- The Pauli $\sigma_z$ operator is written as such in the $\ket{0}$ and $\ket 1$ basis
![[Pasted image 20230908120035.png|120]]
- The Pauli $\sigma_x$ operator in the same basis is written as such
![[Pasted image 20230908120147.png|80]]
- However, in the $\ket +$ and $\ket -$ basis, it is written
![[Pasted image 20230908120220.png|160]]
- In other words, measurement of spin along the $x$ axis using the $x$ basis yields the same eigenvalues as measurement along the $z$ axis using the $z$ basis


---
# Quantum Computing Notes

## 1 Introduction
Quantum computing makes use of two phenomena: superposition, entanglement and interference

Max Planck said in his autobiography was less punchy but equally profound: “A new scientific truth does not triumph by convincing its opponents and making them see the light, but rather because its opponents eventually die, and a new generation grows up that is familiar with it.

Two types of quantum computing: gate-based and quantum annealing (optimisation by minimum energy)

### Classical bit vs qubit
For a classical system of n components, the state can be described by n bits. Whereas for a quantum system of n components (due to superposition) $2^n$ complex numbers are required to describe the state of the system

### Quantum parallelism
Distributive effect of linear operators in quantum mechanics means that a single operator (gate) can be applied to a superposition of states which is identical to applying it to each basis state individually. This speeds up calculation.

### Measurement
Upon measuring a superposition of basis states, the wavefunction collapses to one of the basis states. Probability of obtaining a particular basis state corresponds to magnitude of complex coefficient of each basis state in superposition.


## 2 Basis Set

### X Basis

### Y Basis

### Z Basis

## 3 Gates

### X Gate

### Y Gate

### Z Gate

### H Gate (Hadamard)

### CX (CNOT) Gate

### CZ Gate

### General Controlled-Not Gates

### CCNOT Gate (Toffoli)

---

# Quantum Computation & Quantum Information (Nielsen & Chuang)

## Efficient vs inefficient algorithms
Efficient algorithms are ones that run in time polynomial in the size of the problem solved. In contrast, inefficient algorithms require super-polynomial time (typically exponential).

## Church-Turing thesis
Any algorithmic process can be simulated efficiently using a Turing machine.

## Turing machine model of computation

## Quantum error correcting code and fault-tolerant quantum computation
Unlike analogue computation, quantum computation can in principle tolerate a finite amount of noise and still retain its computational advantages.

## Deutsch's Universal Quantum Computer
One of the great open problems in the field of quantum computation is proving or refuting that a Universal Quantum Computer is capable of efficiently simulating an arbitrary physical system.

Deutsch asked whether it is possible for a quantum computer to efficiently solve computational problems that cannot be efficiently solved on a classical computer, or even a probabilistic Turing machine.

## Shannon's Information Theory
- Shannon's noiseless channel coding theorem quantifies the physical resources required to store the output from an information source
- Shannon's noisy channel coding theorem quantifies how much information it is possible to reliably transmit through a noisy communications channel. To do so, Shannon showed that error-correcting codes could be used to protect the information being transmitted. This gives the upper limit on the noise-protection afforded by error-correcting codes.
- Ben Schumacher provided a quantum analogue to Shannon's noiseless channel coding theorem and in the process defined the qubit as a tangible physical resource, however, no quantum analogue of Shannon's noisy channel coding theorem is known.

## Jargon
- deterministic test
- Church-Turing thesis
- Efficient vs inefficient algorithms
- Randomised algorithms
- Solovay-Strassen test
- Shor's algorithm
- Grover's algorithm (better search through some unstructured search space)