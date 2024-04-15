# Overview
- Second quantisation representation of Hamiltonian
- Map Hamiltonian to qubits using Jordan-Wigner or Bravyi-Kitaev transformations
- Trotterisation to simulate dynamics

# Bravyi-Kitaev Transformation (Paper)
- Quantum simulation of electronic structure requires a representation of fermions by systems of qubits.
- The Jordan-Wigner transformation is probably the most well-known fermion-qubit mapping known.

## Fermionic Simulation Scheme
- Now, consider the following scheme;
![[Pasted image 20230926154010.png|300]]
- First, we encode the fermionic states in qubits
- then we act on the qubit representation with a qubit operator which represents the fermionic operator (obtained by the associated transformation)
- The we invert the encoding to obtain the resultant fermionic state
- The requirement for a successful simulation scheme is that this procedure reproduces the action of the fermionic operator (that path 1 is equivalent to path 2 for all basis states)

- a fermionic simulation scheme can be broken down into two pieces
	- map occupation number basis vectors to states of qubits
	- represent the fermionic creation and annihilation operators in terms of operations on qubits in a way preserves the fermionic anti-commutation relations
- the Jordan0Wigner transformation is then used to write the electronic Hamiltonian as a sum over products of Pauli spin operators acting on the qubits of the quantum computer
- Subsequently the Hamiltonian terms $h_k$ are converted into the unitary gates that are the corresponding time evolution operators

## fermionic systems and second quantisation

### interactions in fermionic systems
- any interaction of a fermionic system can be expressed in terms of products of the creation and annihilation operators $a^\dagger_j$ and $a_j$ which act on the $j^{th}$  orbital
- due to the exchange anti-symmetry of fermions the action of the creation/annhilation operators introduces a phase to the electronic basis state that depends on the occupancy of all orbitals with index less than $j$ in the occupation number representation
- this is done to preserve the Pauli principle
- these operators act on occupation number basis vectors as follows
![[Pasted image 20230926160628.png|400]]

- formally, it is the fermionic anti-commutation relations that enforce the exchange anti-symmetry
![[Pasted image 20230926184241.png|280]]

### Hamiltonian in second quantisation
- the molecular electronic Hamiltonian of interest is
![[Pasted image 20230926184624.png|250]]
- where $h_{ij}$ is a one-electron overlap integral
- where $h_{ijjk}$ is a two-electron overlap integral
- these overlap integrals can be computed classically and input to the quantum simulation as parameters


---

# OpenFermion (Paper)

- workflow for translating a problem in quantum chemistry to quantum computing
	- specify property of interest for particular state of a molecule/material
	- requires specification of positions and identities of atoms in molecule
	- choice of discretisation - transfer from continuous function/variable to discrete counterpart that is numerically evaluable on digital computers


## A) molecule specification and input generation
- the electronic structure problem usually refers to the problem of determining the electronic configuration for a fixed set of nuclear positions (assuming non-relativistic energy scales)
- below we define a particular configuration of H2 in OpenFermion
```python
from openfermion . hamiltonians import MolecularData

geometry = [['H', [0, 0, 0]],
			['H', [0, 0, 0.74]]]

basis = 'sto−3g'
multiplicity = 1
charge = 0
h2 molecule = MolecularData(geometry , basis , multiplicity , charge)
```
- note that the specification of a molecule geometry implicity assumes the Born-Oppenheimer approximation which states that nuclear motion can be approximated as stationary on the timescale of electronic motion
- the ground state electronic energy under the Born-Oppenheimer approximation is therefore a parametric function of the nuclear positions
- hence, when the nuclear positions are specified, the problem can be restated as finding the eigenstates of the following Hamiltonian operator (in the first-quantisation / expressed in atomic units)
	- 1 term - kinetic energy of each individual electronic
	- 2 term - attractive potential between nucleus $j$ and electron $i$
	- 3 term - repulsive potential between each pair of electrons
	- 4 term - constant repulsive term between each pair of nuclei
![[Pasted image 20230926101705.png|450]]
### Hamiltonian diagonalisation and spin
- since we focus on the non-relativistic Hamiltonian, there is no explicity dependence on electron spin
- hence the total electronic spin and its $z$ component (canonically chosen) form good quantum numbers for $H$
- the Hamiltonian can therefore be made block diagonal with separate spin labels for each block
![[Pasted image 20230926111823.png|250]]
- explicitly including this symmetry offers a number of computational advantages
	- small spaces to explore
	- ability to access excited states that are the lowest energy state within a specific spin manifold using ground state methods
- in particular we parametrise these manifolds by the spin multiplicity $2S + 1$
- here the eigenstates of the $\hat S^2$ operator have, by definiton, eigenvalues $S(S+1)$
- hence, when considering the lowest energy singlet state ($S=0$) we have `multiplicity = 1`

### charge
- typically, electronically neutral systems (same number of electrons and protons) are the most stable
- however, sometimes we wish to discuss charged systems in which case we specify the `charge`
- in the case of molecular hydrogen H2, `charge = 0`

### basis set
- finally, to specify the computational problem to be solved, rather than simply the molecule itself, we must specify a set of basis functions
- much thought has gone into optimising special basis sets in chemistry to balance cost and accuracy
- the most common basis sets expressed as sums of Gaussians can be found in the [EMSL basis set exchange](https://www.basissetexchange.org/)
- a very common minimal basis set called **sto-3g** which stands for 3 Gaussians and approximates the Slater-type orbitals is used in this example `basis = 'sto-3g'`


## B) integral generation
- after the specification of the molecule in the previous section, it becomes necessary to do some numerical work in generating the problem to be solved
- in OpenFermion, this is accomplished though plugin libraries that interface with exciting electronic structure codes
- one such interface is the `PySCF` library


### Hartree-Fock and second quantised electronic Hamiltonian
- once one has chosen a specific basis set and enforced the physical anti-symmetry of electrons the electronic structure problem may be expressed exactly in the form of the second quanitized Hamiltonian
![[Pasted image 20230926113308.png|350]]
- the coefficients $h_{ij}$ and $h_{ijkl}$ are defined by the basis set chosen for the problem (sto-3g in this case)
- where $h_{ij}$ is the one electron integral and $h_{ijkl}$ is the two electron integral
- however, the computation of these coefficients can be quite involved
- in many cases it makes sense to perofrm a Hartree-Fock calculation first and transform the above integrals into the molecular orbital basis

## C) mapping to qubits
- after the problem has been recast into the second quantised representation, we must map it to qubits
- electrons are anti-symmetric with respect to particle exchange and indistinguishable
- to contrast, qubits are distinguishable, hence, we must be careful when mapping between the two
- there are now many maps that respect the correct particle statistics, the most common being
	- Jordan Wigner
	- Bravyi-Kitaev
	- Bravyi-Kitaev super fast
- each of the above are supported in OpenFermion
- once a particular transformation has been chosen, we obtain a qubit operator representing the Hamiltonian


---

## glossary

### sparse matrices

### trotterisation
see [[Fermionic Simulation & Trotterisation.pdf]]
