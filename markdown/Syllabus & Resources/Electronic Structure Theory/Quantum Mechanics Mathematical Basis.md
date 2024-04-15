[Quantum Mechanics Mathematical Basis, Faculty of Khan](https://www.youtube.com/playlist?list=PLdgVBOaXkb9Bv466YnyxslT4gIlSZdtjw)

# Quantum Mechanics Mathematical Basis
## Introduction to Vector Spaces
A linear vector space is a set of vectors and associate scalars for which exists a set of defined operations (axioms) for **vector addition** and **scalar multiplication**.
### Axioms of a Linear Vector Space
#### Vector Addition
**Closed under addition**
- If $\psi_1$ and $\psi_2$ belong to $V$, then $\psi_{1} + \psi_{2}$ must also belong to $V$

**Commutativity**
- The order of addition is unimportant such that,
$$\psi_{1} + \psi_{2} = \psi_{2} + \psi_{1}$$

**Associativity**
- Order of addition of groups is unimportant such that
$$\psi_{1} + (\psi_{2} + \psi_{3}) = (\psi_{1} + \psi_{2}) + \psi_3$$

**Zero vector**
- For each $\psi_i$ there is a vector $\vec 0$ such that $\psi_{i} + \vec 0 = \psi_{i}$

**Inverse Property**
- For each $\psi_{i}$ there is a vector, $-\psi_{i}$ such that $\psi_{i} + (-\psi_{i}) = \vec 0$
#### Scalar Multiplication
**Closed Under Scalar Multiplication**
- If $\psi_{1} \in V$ then $a_{1}\psi_{1} \in V$

**Distributive**
$$a_{1} (\psi_{1} + \psi_{2}) = a_{1} \psi_{1} + a_{1} \psi_{2}$$
$$(a_{1} + a_{2}) \psi_{1} = a_{1}\psi_{1} + a_{2}\psi_1$$

**Associativity**
- Order of scalar multiplication of groups is unimportant
$$a_{1} (a_{2} \psi_{1}) = (a_{1} a_{2})\psi_{1}$$

**Identity**
- For every $\psi_{i} \in V$, there exists an identity $\hat I$ such that,
$$\psi_{1} \hat I = \hat I \psi_{1} = \psi_{1}$$

**Zero Scalar**
- There exists a zero scalar such that for any $\psi_{i} \in V$
$$0 \cdot \psi_{1} = \vec 0$$
---

## Introduction to Hilbert Spaces

### Definition
- A **Hilbert Space** is a special kind of linear vector space for which the **inner product** and **outer product** are defined.
- The inner product for a vector in a Hilbert space is defined such that,
$$\bra{\psi_{i}} \psi_{j}\rangle \in \mathbb{C}$$
### Conditions for Defined Inner Product
- Conjugate symmetry,
$$\bra{\psi_{i}} \psi_{j}\rangle = \bra{\psi_{j}} \psi_{i}\rangle^*$$
- Linear with respect to ket,
$$\bra{\psi_{1}} a\psi_{2} + b\psi_{3}\rangle = a\bra{\psi_{1}}\psi_{2}\rangle + b \bra{\psi_{1}} \psi_{3} \rangle$$
- Antilinear with respect to bra
$$\bra{a\psi_{1} + b\psi_{2}} \psi_{3}\rangle = a^{*} \bra{\psi_{1}} \psi_{3}\rangle + b^{*} \bra{\psi_{2}} \psi_{3}\rangle$$
- Positive definiteness,
$$\bra{\psi_{1}}\psi_{1}\rangle = |\psi_{1}|^{2} \geq 0$$
#### Separability (Countable and Dense)
- Hilbert spaces that are **separable** contain a **countable**, **dense subset**
- $\mathbb{R}$ is **separable** because its countable, dense subset is the rational set $\mathbb Q$ 
- $\mathbb Q$ is **countable** because it consists of all numbers that can be expressed as a ratio of integers $\mathbb Z$
- $\mathbb Q$ is **dense** because we can find a rational number arbitrarily close to an irrational number
#### Completeness
- Hilbert spaces contain no *gaps*

### Finite-Dimensional Hilbert Spaces
- May either be real-valued or complex-valued
- Finite number of vectors ($n$ vectors) required to form a complete basis
$$\mathbb{R}^{n} \text{ or } \mathbb{C}^n$$
- The inner product on $\mathbb{R}^n$ is defined as a typical inner product
$$\psi^{T}_{1} \,\psi_{2}$$
- The inner product on $\mathbb{C}^n$ is defined as the complex inner product
$$(\psi_{1}^*)^{T} \,\psi_{2}$$
### Infinite-Dimensional Hilbert Spaces
- Examples include vector space of complex-valued functions
- The inner product is defined by the following integral
$$\bra{\psi_{1}}\psi_{2}\rangle = \int^{\infty}_{-\infty} \psi_{1}^{*} \psi_{2} \,d\tau$$
- This definition of the inner product requires the set of complex-valued functions in our Hilbert space to be **square-integrable** functions
- Therefore, the value of the inner product is finite-valued and defined

---

## Introduction to Dirac Notation

### Ket Notation
- The ket represents the normal form of a vector in Hilbert space, $\mathbb R^{n}$ or $\mathbb C^{2}$
$$\ket\psi = f(\vec r, t) \quad \text{vector in $\mathbb C^n$}$$
### Bra Notation
- The bra represents the complex transpose of a vector in Hilbert space
$$\bra\psi = (\ket\psi^*)^{T}$$
### Braket Notation
- The inner product of two vectors is defined by a bra followed by a ket
$$\bra{\psi_{1}} \psi_{2}\rangle = \mathbb C$$
### Properties

#### Every Ket has a Bra
- Every ket must have a bra in order for the inner product to be defined in a Hilbert space
#### Constant Multiple Property
$$\ket{a\psi} = a\ket\psi \quad\text{ and }\quad \bra{a\psi} = a^*\bra\psi$$
#### Braket Properties
- Conjugate symmetry,
$$\bra{\psi_{i}} \psi_{j}\rangle = \bra{\psi_{j}} \psi_{i}\rangle^*$$
- Linear with respect to ket,
$$\bra{\psi_{1}} a\psi_{2} + b\psi_{3}\rangle = a\bra{\psi_{1}}\psi_{2}\rangle + b \bra{\psi_{1}} \psi_{3} \rangle$$
- Antilinear with respect to bra
$$\bra{a\psi_{1} + b\psi_{2}} \psi_{3}\rangle = a^{*} \bra{\psi_{1}} \psi_{3}\rangle + b^{*} \bra{\psi_{2}} \psi_{3}\rangle$$
- Positive definiteness,
$$\bra{\psi_{1}}\psi_{1}\rangle = |\psi_{1}|^{2} \geq 0$$
- Triangle inequality (equality when $\psi$ and $\phi$ linearly dependent),
$$\sqrt{\bra{\psi + \phi \,} \, \psi + \phi \rangle} \leqslant
\sqrt{\bra{\psi}\psi\rangle} + \sqrt{\bra{\phi}\phi\rangle}$$
- Schwarz inequality (equality when $\psi$ and $\phi$ linearly dependent),
$$\bra{\psi} \phi \rangle^{2} \leqslant
\bra{\psi}\psi\rangle \bra{\phi}\phi\rangle$$
- Orthogonality
---

## Introduction to Operators

### General Notes
- Operators in quantum mechanics that represent a physical observable are Hermitian (self-adjoint $A^{\dagger} = A$)
- Operators in finite-dimensional Hilbert spaces $\mathbb C^n$ are square matrices
- Operators in infinite-dimensional Hilbert spaces are complex-valued functions
- Operators act on kets from the left and bras from the right
$$\hat A \ket{\psi_{1}} = \ket{\psi_{1}^{'}} \qquad \bra{\psi_{1}} \hat A = \bra{\psi_{1}^{'}} $$
$$\bra{\psi_{1}}\hat A \ket{\psi_{2}} \rightarrow \bra{\psi_{1}} \psi_{2}^{'}\rangle \in \mathbb C $$
### Linear Operators
- Matrix multiplication is distributive
- Scalar multiplication is commutative
### Inverse Operators
- The inverse of the linear operator $\hat A$ is also a linear operator $\hat A^{-1}$ 
$$\hat A^{-1} \hat A = \hat I$$
$$(\hat A \hat B)^{-1} = \hat B^{-1} \hat A^{-1}$$
$$(\hat A^{n})^{-1} = (\hat A^{-1})^{n}$$
### Hermitian Operators
$$A = A^\dagger$$
#### Aside on Adjoints
- For scalar $a$, the adjoint is $a^{\dagger} = a^*$
- For the bra/ket vectors, the adjoint is $\bra\psi^{\dagger} = \ket\psi \quad \ket\psi ^{\dagger} = \bra\psi$
- For an operator, the adjoint is $A^{\dagger} = (A^*)^{T}$
#### Properties of Hermitian Operators
![[Pasted image 20231212120304.png]]

### Anti-Hermitian Operators
$$\hat A = - \hat A^\dagger$$
### Unitary Operators
$$\hat A^{\dagger} = \hat A^{-1}$$
### Projection Operators
- Must be Hermitian $\hat A = \hat A^\dagger$
- Must be equal to its own square $\hat A = \hat A^2$
- Classic example of a projection operator is the identity operator $\hat I$
$$\hat I = \hat I^{\dagger} = \hat I^2$$
- The identity operator essentially projects a vector onto itself

#### Properties of Projection Operators
- If two projection operators $\hat p_1$ and $\hat p_2$ commute, then $\hat p_{1} \hat p_{2}$ is also a projection operator.
$$[\hat p_{1}, \hat p_{2}] = 0 \quad\Rightarrow\quad \hat p_{1}\hat p_{2} = (\hat p_{1}\hat p_{2})^{\dagger} = (\hat p_{1}\hat p_{2})^2$$
- A sum of projection operators may also be a projection operator if all projection operators in the sum are **mutually orthogonal**

## Commutators and Eigenvalues

### Commutators
- Can be thought of as the extent to which $\hat A$ and $\hat B$ commute
$$[\hat A, \hat B] = \hat A \hat B - \hat B \hat A$$
- The anti-commutator is defined such that,
$$\{\hat A, \hat B\} = \hat A \hat B + \hat B \hat A$$