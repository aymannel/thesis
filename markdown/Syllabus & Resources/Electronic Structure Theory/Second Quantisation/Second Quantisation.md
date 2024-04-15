# The Second Quantisation

### Introduction
- The second quantisation is the name given to a set of techniques which are very powerful for dealing with many-particle systems
- In a sense it is a different posture towards quantum mechanics. it is quantum mechanics but viewed in a different way
- [[Jordan-Wigner Transformation]] allows for representation of a fermionic operator by $O(n)$ qubit operations
- The [[Bravyi-Kitaev Transformation]] reduces the simulation cost to $O(\log n)$ qubit operations
### General Fermionic Simulation Scheme
1) Map some fermionic state (usually in occupation number representation) to qubits
2) Fermionic-qubit mapping can occur via Jordan-Wigner, Bravyi-Kitaev... transformations
3) We then act on the qubits with some unitary that represents a fermionic operator
4) This mapping must be done in such a way as to preserve the fermionic anti-commutation relations
5) The resulting qubit state is then decoded to yield the resultant fermionic state
6) A successful simulation scheme is one that reproduces the action of the fermionic operator

### Occupation Number Representation (Fermionic)
- Consider $n$ single-particle states, each of which represent a spin-orbital (often HF MOs)
- Each state is either occupied or unoccupied by a 'spinless' particle
- Hence, the full Fock space is spanned by $2^n$ electronic basis states
- However, we actually consider some subspace of this Fock space due to the requirement of exchange anti-symmetry imposed by the fermionic Pauli principle
- Hence, the Pauli principle is implicit in this representation
$$\ket{f_{n-1} \dots f_{0}} \qquad \text{where } f_{j} \in {0, 1}$$
- Where $j$ is the index of the $j^{th}$ spin-orbital
- Note that this representation is actually shorthand for a given Slater determinants, since to construct a Slater determinant, all we must know is which spin orbitals are occupied and which are not
- The space spanned by these occupation number 'vectors' is known as the Fock space
- These Slater determinants form an orthonormal basis for the Fock space for a given system

### Creation and Annhilation Operators
- Any interaction in a fermionic system can be expressed in terms of the products of the creation and annhilation operators $\hat a_j^\dagger$ and $\hat a_j$ which act on the fermion in the $j^{th}$ spin-orbital
- Due to the exchange anti-symmetry of fermions, the action of the creation/annhilation operators introduces a phase to the basis state that depends on the occupancy of all the spin-orbitals with index less than $j$ in the occupation number representation
![[Pasted image 20230926160628.png|450]]
- Take the following examples (where there are four spin-orbitals in the Fcok sub-space)
$$\hat a_2^{\dagger} \ket{001} = - \ket{011}$$
$$\hat a_{2} \ket{011} = - \ket{001}$$
$$\hat a_{2}^{\dagger} \ket{011} = 0$$
$$\hat a_{2} \ket{001} = 0$$
- Note that $\hat a^{\dagger} \ket{1}$ and $\hat a \ket{0}$ yield the zero vector, **not** $\ket 0$. For this reason, these operators are neither Hermitian nor unitary
- Formally it is the fermionic anti-commutation relations that enforce the exchange anti symmetry (see next section)
- Observables must be independent of the representation used, hence
	- Expectation values of first quantised operators must be equivalent to those in the second quantisation
	- Since particle number is conserved in the first quantisation, so it must be in the second
	- Therefore, there must always be an equal number of creation and annhilation operators

#### Anti-Commutation Relations
- Formally, for fermionic systems, the exchange of any two identical particles is anti-symmetric
- In the second-quantisation, this is expressed in terms of the anti-commutation of creation and annhilation operators such that the permutation of the labels results in anti-symmetry
- In fact, we find that the phase factor discussed in the previous section are automatically kept track of by the anti-commutation relations of the creation/annhilation operators
$$[\hat a_{j}, \hat a_{k}]_{+} = \hat a_{j} \hat a_{k} + \hat a_{k} \hat a_{j} = 0  \quad\Rightarrow\quad \hat a_{j} \hat a_{k} = - \hat a_{k} \hat a_{j}$$
$$[\hat a_{j}^{\dagger}, \hat a_{k}^{\dagger} ]_{+} = \hat a_{j}^\dagger \hat a_{k}^\dagger + \hat a_{k}^\dagger \hat a_{j}^\dagger = 0  \quad\Rightarrow\quad \hat a_{j}^\dagger \hat a_{k}^\dagger = - \hat a_{k}^\dagger \hat a_{j}^\dagger$$
$$[\hat a_{j}, \hat a_{k}^{\dagger} ]_{+} = \hat a_{j} \hat a_{k}^\dagger + \hat a_{k}^\dagger \hat a_{j} = \delta_{jk} \hat{1}$$

#### Occupation Number Operators
- The following product $\hat a^{\dagger}_{j} \hat a_{j}$ 'counts' the occupation number of spin orbital $j$ (either 0 or 1 for fermions)
- This corresponds to an operator known as the 'number' operator
$$\hat n_{j} = \hat a^{\dagger}_{j} \hat a_{j}$$
- To see this in action, consider the following
$$\hat n \ket{0} = \hat a^{\dagger} \hat a \ket 0 = \hat a^{\dagger} (0) = 0$$
$$\hat n \ket{1} = \hat a^{\dagger} \hat a \ket 1 = \hat a^{\dagger} \ket {0} = \ket{1}$$
- Such that the eigenvalues of $\hat n_{j}$ are $0$ and $1$, which corresponds to the possible occupation number for a single fermionic spin-orbital
- It follows then that summing all occupation number operators in the Fock space, we obtain the Hermitian operator
$$\hat N = \sum\limits_{P=1}^{M} \hat a^{\dagger}_{P} \hat a_{P}$$
- Which acts on a given state $\ket \psi$ in the occupation number representation and returns the total number of electrons in that state
### Second-Quantised Hamiltonian
- The molecular electronic Hamiltonian of interest can be expressed in terms of creation and annhilation operators as such
![[Pasted image 20230926184624.png|250]]
- Where $h_{ij}$ is the one-body overlap integral and $h_{ijkl}$ is the two-body overlap integral
- Note that the fermionic exchange anti-symmetry is now implicit in the second-quantised form of the Hamiltonian as a result of the creation and annhilation operators obeying the fermionic anti-commutation rules
- The Hamiltonian can therefore only contain terms with up to four operators (two creation and two annhilation) as a result of the two-body nature of Coulomb's law
#### One-body integral $h_{ij}$ 
- The one-body integral can be expressed as the following expectation integral
![[Pasted image 20230928122801.png|300]]
- The physical significance of which is the;
	- kinetic energy of a given electron 
	- the potential interaction of the given electron with the nuclear electric fields

#### Two-body integral $h_{ijkl}$
- The two-body integral can be expressed as the following expectation double integral
![[Pasted image 20230928122930.png|420]]
- The physical significance of which is the repulsive interaction between a given pair of electrons
#### Integral Calculation
- These integrals are computed classically and input as parameters into the quantum simulation
- Note that $h_{jk}$ and $h_{ijkl}$ depend on the nuclear coordinates $R$ and are defined by a specific choice of basis set (for instance sto-3g)
- In many cases, however, due to the difficulty of calculating these coefficients, it is often computationally cheaper to perform a Hatree-Fock calculation first and transform these integrals into the molecular orbital basis

#### Intuition for Simple Second-Quantised Hamiltonians
- The following term in the Hamiltonian for some system represents the energy of an electron hopping from spin-orbital $j$ to spin-orbital $i$
$$h_{ij} \hat a^{\dagger}_{i} \hat a_{j} \ket \psi$$
- Similarly, the following term represents the energy of two electrons in spin-orbitals $k$ and and $l$ scattering off each other and ending up in spin-orbitals $i$ and $j$
$$h_{ijkl} \hat a^{\dagger}_{i} \hat a^{\dagger}_{j} \hat a_{k} \hat a_{l} \ket\psi$$
- If $i = l$ and $k = j$ then the following term gives the energy cost associated with two electrons being near one-another
$$h_{ikki} \hat a^{\dagger}_{i} \hat a^{\dagger}_{k} \hat a_{k} \hat a_{i} \ket\psi$$
- Next, consider the following Hamiltonian
$$\hat H = a^{\dagger}_{0} a^{\dagger}_{1} a_{1} a_{0} - a^{\dagger}_{1} a^{\dagger}_{0} a_{1} a_{0}$$
- Because of the anti-commutation rules of the creation operators, we can reexpress this as
$$\hat H = a^{\dagger}_{0} a^{\dagger}_{1} a_{1} a_{0} - (- a^{\dagger}_{0} a^{\dagger}_{1} a_{1} a_{0}) = 2 a^{\dagger}_{0} a^{\dagger}_{1} a_{1} a_{0}$$
- More generally, we can show that
![[Pasted image 20230928143329.png|300]]



### Approximate Solutions to Hamiltonian
- Consider the second quantised Hamiltonian in which we neglect the repulsive electron-electron term
- Our Hamiltonian now describes a system of non-interacting electrons
- We can define a suitable basis for this fictitious system as the set of molecular orbitals that diagonalises the non-interacting Hamiltonian
- These molecular orbitals are typically linear combinations of orbitals localised around each atom (atomic orbitals)
- In practice, these molecular orbitals form a poor basis, hence, instead a mean field approximation (Hartree-Fock) can be used
![[Pasted image 20231002164344.png|300]]
- 


---
## Resources
- [Microsoft Azure Second Quantisation](https://learn.microsoft.com/en-us/azure/quantum/user-guide/libraries/chemistry/concepts/second-quantization)
- [[Second Quantisation - Gabriel Landi]]
- [[Bravyi-Kitaev Transformation]]
- [[Examples of Second Quantisation]]
- [[Barford Second Quantisation]]

---

### Key insight about fermionic correlation
- electron correlation. imagine a non-interacting gas of fermions. the fermions are **still** correlated as a result of the Pauli principle, which states that the total fermionic wavefunction must be anti-symmetric with respect to the exchange of any two identical fermions. the implications of the Pauli principle is therefore that no two fermions can occupy the same quantum state (including translation states) and therefore the probability of finding two fermions near one another decreases as their separation decreases.