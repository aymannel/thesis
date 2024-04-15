# Quantum Dynamics

#### classical dynamics
- the position of a particle evolves according to Newton's second law of motion
- thus given an initial position, evolution time, and the forces activing on a system we can find $x_{(t)}$
- Hamiltonian mechanics was actually first introduced to do classical mechanics
- the Hamiltonian represents the total energy of an arbitrary classical particle
- Newton's laws of motion can subsequently be recovered from the classical Hamiltonian

#### quantum dynamics
- quantum dynamics seeks to understand how a quantum state $\ket{\psi}$ evolves over time
- specifically, given the initial state $\ket{\psi_{(0)}}$, an evolution time $t$ and a specification of the quantum dynamical system (via the Hamiltonian), $\ket{\psi_{(t)}}$ is sought
- the Hamiltonian completely specifies the dynamics of any closed quantum system
- the Hamiltonian in quantum mechanics differs from its classical analogue in that it is a matrix (specifically a Hermitian matrix)
- the requirement that the Hamiltonian in quantum dynamics is hermitian ensures that the eigenvalues are real-valued
- the process of taking a classical Hamiltonian and using it to find its quantum analogue is known as **canonical quantisation**
- we find that the time-dependent Schrödinger equation is some partial differential equation that specifies the dynamics of a closed quantum system
$$i \frac{\partial}{\partial t} \ket{\psi_{(t)}} = \hat H_{(t)} \ket{\psi_{(t)}}$$
- the solution to the differential equation can be expressed in the following form (where H is the time-independent Hamiltonian / constant wrt $t$)
$$\ket{\psi_{(t)}} = e^{-iHt} \ket {\psi_{(0)}}$$
- here, $e^{-iHt}$ is a **unitary** matrix which means that there exists a quantum circuit that can be designed to perform it since quantum circuits can closely approximate any unitary matrix
- the process of finding the quantum circuit that approximates this unitary is known as **dynamical quantum simulation**