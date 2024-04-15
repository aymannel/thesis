# Jordan-Wigner Transformation

### Qubit Occupation Number Basis
- The form of the occupation number representation basis suggests the following identification between electronic basis states and qubit states
![[Pasted image 20230928112814.png|400]]
- That is, we allow each qubit to store the occupation number of spin-orbital $j$

### Fermionic-Qubit Mapping of Creation & Annhilation Operators
- In order to perform a quantum simulation, we must map the fermionic creation and annhilation operators onto qubit operators
- Very much in the same way as their fermionic operator analogues, the qubit operators behave as such
![[Pasted image 20230928113101.png|350]]
- Note that in order to do this mapping, we must preserve the fermionic anti-commutation relations to enforce the fermionic exchange anti-symmetry in our quantum circuit
- This can be done by expressing the qubit creation/annhilation operators in terms of Pauli matrices
![[Pasted image 20230928113245.png|350]]
- The mutal anti-commutation of the three Pauli matrices allows us to recognise that $\hat Q^{\pm}$ anti-commutes with $\sigma^{z}$ 
- Thus by representing the fermionic creation/annhilation operators $\hat a^{\dagger}$ and $\hat a$ with $\hat Q^{\pm}$ and $\sigma^z$ on all other qubits with index less than $j$, we ensure that our qubit operators will obey the fermionic anti-commutation relations
- Put differently, the states of our quantum computer will acquire the same phases under the action of our qubit operator as do the electronic basis states under the action of the creation/annhilation operators
- The effect of the string of $\sigma^{z}$ gates is to introduce the required phase change of $-1$ if the parity of the set of qubits with index less than $j$ is odd and and $1$ if it is even
- The fermionic creation/annhilation operators can then be completely represented in terms of the Pauli qubit gates as follows
![[Pasted image 20230928113820.png|400]]
- A more compact notation however is
![[Pasted image 20230928113925.png|300]]
- Where $Z_i^{\rightarrow}$ is the parity operator (with eigenvalues $\pm 1$) and ensures the correct parity
![[Pasted image 20230928113940.png|200]]


### Efficiency of the Jordan-Wigner Transformation
- As a consequence of the non-locality of the parity operator, the number of additional qubit operators required to simulate a single fermionic operator scales as $O(n)$


## Resources
- [[Bravyi-Kitaev Transformation]]

---


- derive the first quantised hamiltonian for a number of different examples
- derive the qubit hamiltonian in terms of pauli strings from the second quantised hamiltonian of some systems
- derive the second quantised hamiltonian of a system from the first quantised hamiltonian