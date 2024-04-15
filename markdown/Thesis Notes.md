# navigating latex project
- `<leader> n` - next buffer
- `<leader> p` - previous buffer
- `<leader> d` - close buffer
- `<leader> kk` - make github checkpoint

## sorted to do
### thesis plan
- plan
	- references 
	- literature that you still need to read
	- introduction section make all diagrams etc
	- use diagrams from presentation
	- code to implement (lowest priority)
- plan thesis in obsidian and copy paste relevant diagrams from jupyter notebook
- you only have a limited amount of time to do your thesis
- therefore, prioritise research over coding
- that said, if as you do your research want to implement something new you can
- keep track of suggested feature ideas / perhaps formalise this and use github

### questions for richie
- try derivation showing that cliffords commute through phase gadget
- ask about why this happens
- is it because cliffords are unitary and hermitian

### general notes
- relate content to title of thesis!
- diagrammatic design of ansatze for quantum chemistry
	- explain how representing excitation operators in the zx calculus is beneficial as you're basically storing the 'true' most general form of the operators
	- you can hence decompose the operators as you see fit
	- write zxfermion methods for optimal circuit synthesis for different quantum architectures

### literature search
- do literature search of existing and new literature
	- find a bunch of papers by topic
	- read abstracts and and put into spreadsheet
	- those that are interesting store quotes or ideas to reference


### section ideas
- looking at [[A Generic Compilation Strategy for the Unitary Coupled Cluster Ansatz.pdf]], you should have a section on the commutation relation that partitions sets of mutually commuting strings
- you should look at bigger system sizes and find the pattern
- since all molecular orbitals follow the same pattern as tew said

### formatting & VCS
- set up github for thesis
- look at font of page numbering
- why is background
### theory insights
- what's the physical significant of the individual phase gadgets at the end? how do they relate to the wavefunction?
- paulis turn into phase gadgets when conjugated by cnots  
- that is they effectively measure the parity of additional qubits  
- what is the significance of this?
- investigate higher order UCC
- have a think about the creation/annhilation operators and the hamiltonian eigenvalue associated with particular
- DUDE, does the X/Y pattern along a qubit somehow represent the bonding/antibonding orbitals?
- each time you add a cnot the pattern along the control changes eventually becoming lowest energy level. watch the bottom qubit
- looking along the top two qubits, try to pair phase gadgets in double excitation operator in YX-XY pairs cos these behave like your two body ones
- whats the chemical significance of the XX and YY pairs then? is there something you can do to these?
- what the physical significance of the XX and YY 
- XX becomes XI, YY becomes XZ
- but XY-YX becomes a controlled rotation
![[Pasted image 20240411014308.png]]


### things to try
- have a look at applying CZ instead/as well as CX. look at tableau cheat sheet

### intermediate controlled rotation structure
- successively conjugating by cnots generates localised controlled y rotations but ALSO controlled x rotations
- also the bottom two qubits fuse! what is this structure? look at the matrix 
- each operator can be 'paired' so to speak to give some intermediate controlled rotation structure
![[Pasted image 20240411024336.png]]

![[Pasted image 20240411150545.png|500]]
