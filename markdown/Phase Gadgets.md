# Phase Gadgets
## 1) Introduction
"This chapter introduces the phase gadget and the Pauli gadget, and explains why they are the natural way to reason with parameterised quantum circuits" p27 [[Diagrammatic Design & Study of Ansätze for QML - Richie Yeung]]


## 2) Algebraic Structure
"To understand the power of phase polynomials, we will study the unitaries represented by phase gadgets, which can be used to describe the dimensionality of a parameterised phase polynomial. Diagrammatically, a phase gadget takes its inputs in the Z basis, copies it, XOR’s the bits together, and multiplies the state by exp(−iθ/2) or exp(iθ/2) depending on the parity. One can think of the phase gadget as a many-qubit generalisation of the Z rotation gate." p31 [[Diagrammatic Design & Study of Ansätze for QML - Richie Yeung]] and [[On the controlled-NOT complexity of controlled-NOT–phase circuits]]

"Pauli gadgets occur naturally in quantum simulations where a Hamiltonian is decomposed into a sum of Pauli tensors and Trotterised [theory of VQE]." [[Phase Gadget Synthesis for Shallow Circuits]] p2

![[Pasted image 20240415105606.png]]


"The decomposition law gives the canonical way to synthesise a quantum circuit corresponding to a given phase gadget. However, from the zx-calculus form, it’s immediate that phase gadgets are invariant under permutation of their qubits, giving the compiler a lot of freedom to synthesise circuits which are amenable to optimisation. As a simple example, the naive ∧X ladder approach, shown in Figure 2, requires a ∧X-depth of 2(n−1) to synthesise an n-qubit phase gadget; replacing this with a balanced tree yields a ∧X depth of 2⌈logn⌉. Note that the quantity of ∧X gates used is still (and always will be) 2(n−1), but we can still obtain benefits with respect to depth." p4 [[Phase Gadget Synthesis for Shallow Circuits]]

![[Pasted image 20240415105749.png]] 

## 3) Commutation Relations


---

## references
- [[Diagrammatic Design & Study of Ansätze for QML - Richie Yeung]]
- [[Phase Gadget Synthesis for Shallow Circuits]]