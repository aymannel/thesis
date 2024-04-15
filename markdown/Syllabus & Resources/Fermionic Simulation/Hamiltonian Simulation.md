## motivation for Hamiltonian simulation
- quantum systems are described by Hamiltonians
- for a system of $n$ particles (spin up or spin down), the Hamiltonian is a square matrix of size $2^{n}\times 2^{n}$ 
![[Pasted image 20230929095239.png|150]]
![[Pasted image 20230929095250.png|200]]
- the state vector of a quantum system lies in a quantum space whose dimension ($2^n$) whose dimension grows exponentially with the size of the system
- the evolution of a closed quantum system is unitary (reversible) and is given by the time-dependent Schrödinger equation
![[Pasted image 20230929095542.png|150]]
- The solution of the time-dependent Schrödinger equation is the state of a system after evolution time $t$ (where $\hat H$ in the solution is time-independent)
![[Pasted image 20230929095646.png|170]]
- The problem and principal motivation for quantum computing is that exponentiating the time-indepedent Hamiltonian is very hard (since it may be sparse but exponentially large)
- We can define the time evolution unitary operator $\hat U$ (where $\hat U^\dagger \hat U = \hat 1$) as $\hat U = e^{-i\hat H t}$

**Problem Statement**
- Given a Hamiltonian $\hat H$ of dimensions $2^{n} \times 2^{n}$ 
- A system of $n$ qubits whose state exists in $2^{m}$ vector space
- At time $t$
- And maximum simulation error $\epsilon$
- We must find the optimal sequence of computational gates that implement time evolution such that the difference between simulated time evolution and ideal evolution is less than $\epsilon$
![[Pasted image 20230929100240.png|150]]
- The spectral norm of matrix $\hat A$ is the largest eigenvalue of this matrix

## how to simulate any Hamiltonian in 5 steps
- Assume Hamiltonian simulation occurs on universal quantum computer with gate based model
- Define a model of Hamiltonian as some unitary $\hat U = e^{-i\hat H t}$
- Decompose target Hamiltonian into linear combination of (tensor) products of Pauli operators
$$\hat H = \sum_{l=1}^{L} \hat H_{l} \qquad \hat H_{l} = c_{l} \hat A_{l}$$
- Trotterisation: first check if local terms commute. If they do, one can decompose the exponent without introducing any error
![[Pasted image 20230929101123.png|300]]
- If they do not commute, apply the Lie-Trotter product formula with the correct number of Trotter steps
![[Pasted image 20230929101156.png|300]]
- Translate each exponentiated local Hamiltonian (for each trotter step) into a quantum circuit
![[Pasted image 20230929101253.png|200]]
- Then obtain expectation value of unitary simulating quantum dynamics of system. This may involve initial state preparation
$$\bra\psi \hat U \ket\psi$$


## Evolution under the action of Pauli operators
- 