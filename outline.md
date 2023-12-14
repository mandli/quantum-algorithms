<table>
 <tr align=left><td><img align=left src="https://i.creativecommons.org/l/by/4.0/88x31.png">
 <td>Text provided under a Creative Commons Attribution license, CC-BY. All code is made available under the FSF-approved MIT license. (c) Tom Marshall and Kyle Mandli</td>
</table>

# Developing Quantum Intuition for Developing Quantum Algorithms

## Authorship

The first draft of this outline was conceived and written by Tom Marshall, with inspiration drawn from the published works and presentations of Naomi Nickerson and Mihir Pant, and also my own interests in entanglement, decoherence, and the quantum-to-classical transition.  Kyle Mandli has made substantive contributions to this draft, and I’ve drawn much inspiration and motivation from many colleagues too numerous to mention.  Going forward, this work will be an open-source communal effort, and individual authorship credit will be taken as each author deems appropriate.

## Introduction

This document outlines a Seminar Course on quantum algorithm development, with variations targeted at several different audiences, that will be ported to a GitHub repository for broader co-development.  Kyle Mandli of Columbia has agreed to host the repository, and other faculty from Columbia, NYU, and elsewhere will be invited to participate.  Bloomberg engineers (and others) will be invited to participate freely, the benefits being that such participation will further their own education and experience, and also a version of this Course will be suitable for Bloomberg-internal use.

This Seminar Course is intended to supplement more traditional approaches, not to replace them.  Although a strong foundation in quantum computing and a familiarity with classical algorithms is neither a prerequisite for this Course nor an objective per se, and the curriculum is intended to be adaptable to a broad range of student backgrounds, the material will best be absorbed and built upon by students who do indeed have such skills, for example advanced undergraduates and Masters students in Quantum Computing (QC).

### A Whimsical, Illustrative Analogy of our Vision

A unique feature of this course is that it focuses on building intuition and a big-picture view of quantum resources and real-world problem spaces.  If the reader will permit a bit of whimsy and exaggeration, we offer the following analogy of our vision of the role of this Course.

>Where many courses in quantum computing offer the student, metaphorically speaking, a set of Lego blocks and guidance on how to render things with them, we hope to encourage the student to envision an aspect of the world artistically and then to render that vision using whatever media seem most appropriate – a digital camera, oil and canvas, Lego blocks, or perhaps some new multi-media form not yet imagined.

### Motivation

The promises offered by QC – and the amount of investment in the field – are well known and need not be repeated here, except to reiterate that QC will be commercially relevant at some point, and so is an important educational topic now.

The ultimate value of QC will be in the real-world problems that can be solved, and that of course will require “quantum software”, which will entail significant interaction with conventional classical software.  While there has been great progress in developing quantum algorithms, including quantum-classical hybrid algorithms, still there is at present no systematic approach to the topic.  We cannot yet offer such a systematic approach, but that goal motivates this Seminar Course.

Our intent is to develop a “quantum intuition” at a level deeper than is typically presented to students of QC and quantum algorithms, in the expectation that such facility will help the student/researcher to see connections among the available “quantum resources” on the one hand, and the specific mathematical details of the problem(s) to be solved on the other.

#### Pedagogical and Psychological Support for the Importance of Intuition
A recent Physics Today article (August 2021), [Intuitive or rational? Students and experts need to be both](https://physicstoday.scitation.org/doi/pdf/10.1063/PT.3.4813), documents the efficacy of so called Dual-Process Theories – as expounded on by Nobel Laureate Daniel Kahneman in [Thinking, Fast and Slow](https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow) – where “fast” intuitive cognition and “slow” rational analysis play equally important roles in developing expertise.


### Intended Audience and Scope

This Course Outline is designed to be flexible, and to be adapted to a wide range of possible audiences.  Since the Course starts with the basics, it could – on the one extreme – be used as an introductory survey course, since it covers a broad range of topics, although that’s not its primary intent.  In this case, the material can be presented in a “museum tour” manner, with only rudimentary assignments.  At the other extreme, the Course could be offered as a Research Seminar, setting the stage for independent investigations into any of the topics which are touched on, but for which there is not a large body of literature at present.

The middle-of-the-road vision is that the Course can supplement a standard introductory course, and the level of rigor can be adjusted to suit the needs of the particular group of students.

At all levels of presentation/audience, building intuition – and a deeper understanding of the problem space – is central.  The Course was originally conceived to be useful to technical professionals who will be called upon to make or advise on business decisions as QC technology emerges into the marketplace.  As such, the emphasis is on breadth, at the expense of having insufficient time for uniform rigor throughout the course (except, as mentioned above, the course can be a springboard to individual research projects when presented to a more advanced group).

### Exposure to the Primary Literature

Whatever the level at which the Course is presented, a key element of intuition-building is to expose the participants to the primary literature at a level that would typically be considered “beyond their abilities to absorb”, at least in the time allotted for each individual paper.  This encourages building cognitive models – which may well be wrong at first – that will be refined as the student progresses.  This approach in turn engenders making “intuitive cross-connections” among several different disciplines and sub-disciplines – a valuable facility that will be encouraged in all aspects of the Course.

### Assignments and Grading

This Course is envisioned as a “pass/fail” Seminar Course, with little emphasis on traditional assignments and grading.  Assignments may be given ad hoc, with no expectation of success, i.e., “journey and not destination”.  This seems fair given the breadth of materials covered and the fact that there is no coherent discipline of quantum algorithm development.  Individual instructors are of course free to modify this approach to meet other needs.

### Mechanical Notes on This Document

Although some considerable care and thought went into the initial version of this document, our aim was to get it into as many hands as possible as quickly as possible.  We expect that there will be many changes as the Course itself evolves, although we hope that the spirit of intuition development –  and, in particular, the intentionally ambitious breadth and depth –  will survive, at least as reference materials for students and teachers.

We expect that references will be added, deleted, and moved extensively to and from the main syllabus and the Appendices.  In particular, many Units have few or no references, a deficiency that will be addressed as work progresses communally.

This document is under active development and should not be considered stable.


## Outline of the Seminar Course

### Overview

The course currently comprises nine units, numbered 0-8, with Unit 0 more closely resembling a standard introduction, or “prerequisite review”, but still inflected with our intuitive approach.

After the “enrichment introduction” to qubits and sequential-gate-based QC (SGQC), the fully equivalent but conceptually very different measurement-based QC is presented in Unit 1.  Illustrating the equivalence is the main point, but the Unit also sets the stage for Unit 2, which covers the more modern and practical approach of photonic QC, which is indeed a measurement-based approach, but with quantum resources generated and consumed (measured) constantly, rather than the initial cluster-state approach that characterizes true measurement-based QC.

It is in Unit 2 where the notion of error correction is explored, but via the vehicle of “fault-tolerant channels” as the optical QC literature calls them, which is perhaps a more visual geometric (topological, actually) rendering of error correction.  Consistent with our mission, this rendering provides an intuitive sense of resource consumption, and may possibly offer hints that will help in improving the efficiency of algorithms.

Unit 3 covers analog, or adiabatic quantum computing (AQC).  Although AQC is not truly a universal, it does have significant overlap with other modes of QC, and, in particular, may be an interesting candidate for “triple hybrid QC”, with SGQC and AQC each being stitched together as individual quantum processing units (QPUs) by conventional digital software.

Unit 4 presents a brief survey of state-of-the-art real-world applications – more to show how messy and distant such solutions currently appear than to instruct in best practices (although such techniques are indeed our best practices at the moment).

Unit 5 revisits Unit 0.4 in greater depth, covering many different hardware approaches.  Attention is paid to sources of error, and to approaches to error correction, building on the foundation laid in Unit 2.

Unit 6 discusses quantum memory, both its theoretical usefulness and the hardware challenges of realizing such devices.

Unit 7 explores classical algorithms, focusing on approximation techniques and also mappings from one problem domain to another.  Clearly, even a small part of this topic could be an entire graduate degree program, so the idea is to curate a few illustrative examples and cover notions of approximation and efficiency, with an eye towards their quantum counterparts.

Unit 8 returns to the topic of quantum algorithms, choosing a middle ground between the very basics presented in Unit 0 and the less approachable material in Unit 4.  The hope as of this writing is that concepts from the previous Units can begin to be interwoven to explore novel approaches to simple “toy problems”.

As mentioned above, the course will make use of the primary literature whenever possible, even at the expense of clarity.


### Unit 0: Introductory Overview of The Qubit and its Uses

Unit 0 covers typical “introductory” topics, as may be found in any course or online tutorial, and indeed we draw on examples from Qiskit, and reference the Qiskit literature, e.g.,
[Learn Quantum Computation using Qiskit](https://qiskit.org/textbook/preface.html)  

However, our focus is on making tangency with the fundamentals of quantum mechanics, and on building a conceptual and intuitive framework that are at the heart of this Seminar Course.

#### Unit 0.0: Historical Overview of Quantum Theory

Unit 0.0 briefly reviews the history of quantum mechanics, emphasizing that there is no “derivation” of quantum theory, but rather it was developed – intuitively – to address issues with classical theory.  The progression from Newton’s laws to the Lagrange equations to the Hamilton equations to the Hamilton-Jacobi equation to the Schrödinger equation is shown for intuitive illustration.  For completeness, the Dirac equation and second quantization (quantum field theory) are also shown.  The idea is not to teach anything about the use of these equations, but to show the various forms that the mathematics has taken to address what is, at root, the same physical system.

#### Unit 0.1: Basics of the Quantum Two-Level System

Unit 0.1 introduces the basics of a quantum two-level system: Choosing an (arbitrary!) basis, which is called "the measurement basis" and whose basis vectors are arbitrarily called |0> and |1>; the state vector; rotations of the state vector; the Bloch sphere (and the Q sphere, which includes the (irrelevant) global phase of a single qubit); single-qubit superposition; etc.  Real-world physical qubits are introduced to tie the abstraction to reality, and to focus on exactly how general the abstraction is, and will be revisited later in the Unit.

##### Measurement and Weak Measurement

Measurement in quantum computing is a critical concept, and weak measurements are not typically considered in an introductory course, but are of critical conceptual importance, and are part of the algorithm designer’s tool kit.  This Unit also lays the foundation for Measurement Based Quantum Computing in Unit 1.

[Interaction-Free Measurement](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.74.4763)  
[Quantum feedback with weak measurements](https://arxiv.org/pdf/quant-ph/9905064.pdf)  
[Demystifying Weak Measurements](https://arxiv.org/ftp/arxiv/papers/1702/1702.04021.pdf)  
[Weak Measurement (Wikipedia)](https://en.wikipedia.org/wiki/Weak_measurement)  

##### Unit 0.2: Multi-Qubit States

Unit 0.2 introduces two-qubit states (and in general multi-qubit states) and the notion of entanglement. Superposition per se has no classical analog, but it is described by probabilities that are classically familiar. Entanglement is more than just superposition. It certainly has no classical analog, but even the probabilities seem to defy all classical intuition. Formally, the Bell Inequalities are violated.  The significance of entanglement in quantum algorithms is explored.  The Q-Sphere is revisited to show that the phases of individual qubits in a multi-qubit state are indeed relevant.

##### Unit 0.3: Quantum Gates 

Unit 0.3 introduces "gates", which are just arbitrary unitary transformations on one or more state vectors (quantum states, or “strings of qubits”). Certain gates can entangle two or more previously separate quantum states.

##### Unit 0.4: Introduction to Physical Qubits

Unit 0.4 revisits the physical qubit in several different technologies.  Physical implementations of gates on these "simple" qubits are then discussed, to tie the abstractions yet more tightly to the real world.  Both the practical and conceptual aspects of decoherence are discussed.

##### Unit 0.5: What Quantum Algorithms are Not

Unit 0.5 presents the cautionary tale, championed by Scott Aaronson, that quantum computers do not explore 2n possible solutions in parallel.  The double-edged sword that is linearity and the otherwise-well-known limitations of quantum measurement thwart this grand vision.

This Unit, cast in the negative, is the core of our vision of what algorithms need do:  Opportunistically exploit constructive and destructive interference among the “parallel solutions” so that measurements report “correct” solutions.  There is, of course, no general recipe for doing so,

##### Unit 0.6: Hybrid Algorithms

Unit 0.6 builds on the otherwise-pessimistic Unit 0.5 by introducing a broader notion of hybrid algorithms.  The Unit forward-references current hybrid approaches touched on in Unit 0.7, and explored more fully in Unit 8, but introduces the relatively-infrequently-discussed notion of using a quantum processor unit (QPU) (which may or may not itself be used in a “traditional hybrid mode”) to get an approximate solution of sufficient precision to seed a purely-classical algorithm.
We also explore the notion of an architecture of multiple different QPUs orchestrated by a conventionally constructed program.

##### Unit 0.7: Quantum Algorithms

Unit 0.7 explores some very basic algorithm materials at the level of Qiskit tutorials. Examples are Amplitude Estimation, Phase Estimation, Quantum Fourier Transformation, VQE, QAOA, etc. The idea is to see these perhaps-familiar algorithms in a slightly different perspective, not to "master" them, as might be expected in a different course.

[Optimal Universal Programming of Unitary Gates](https://arxiv.org/pdf/2007.10363.pdf) [(PRL)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.125.210501)  


#### Unit 1: Measurement-Based QC – A Further Glimpse of What the Quantum Can Do

Unit 1 builds on the “conventional” view of SGQC by showing a completely different, but fully equivalent approach:  Measurement-based quantum computing (MBQC).  MBQC can in principle be implemented on any hardware but is more well-suited to some systems than to others.  MBQC leverages the intricacies of entanglement more transparently than sequential gate-based QC, and highlights the fact that SGQC is limited to one-, two-, and three-qubit gates for practical, not fundamental reasons.  The Unit reinforces the lesson that there are many different implementation choices, even in the same basic hardware, that are the same mathematically, even if they’re very different physically.

A key point of this Unit is to show how what we thought we knew – however tenuously – from Unit 0 is very far from the whole physical picture, and by following the abstract math, one can find fully equivalent sets of operations/interactions that, at first, look nothing like each other.  Developing this perspective is the ultimate goal of quantum algorithm development – although this Unit is offered as an analogy only, since we don't have any general heuristics for doing these things at the algorithm level.

Also, this Unit guides us through the "elementary" quantum math to show that the two paradigms (MBQC and, SGQC) are completely equivalent when implemented ideally, but they have very different real-world implementation difficulties and sources of error.  Understanding and keeping an eye on sources of error is just the sort of "quantum intuition" that we're trying to build, even though, ironically, in the ideal world all of the above can be ignored!

[Efficient Linear Optics Quantum Computation, Knill, Laflamme, and Milburn (2000)](https://arxiv.org/pdf/quant-ph/0006088.pdf)  
[Persistent Entanglement in Arrays of Interacting Particles, Briegel and Raussendorf, PRL 86 910 (2001)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.86.910)  
[A One-Way Quantum Compute, Raussendorf and Briegel, PRL 86 5188 (2001)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.86.5188)  
[Resource-Efficient Linear Optical Quantum Computation, Browne and Rudolph, PRL 95 010501 (2005)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.95.010501)  
[Measurement-Based Variational Quantum Eigensolver](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.126.220501)  


#### Unit 2: Photonic Computing – A Vehicle for Developing Quantum Intuition

Unit 2 builds on the conceptual basis of quantum computation developed in previous Units by exploring a specific approach to photonic QC that uses MBQC (or “Fusion-Based”, FBQC) concepts to develop a more efficient and scalable architecture, as exemplified by Psi Quantum.  Specifically, Unit 2 covers the Psi Quantum Mihir Pant lecture on FBQC, and then Naomi Nickerson's three-hour tutorial on error correction, surface code, stabilizer states, syndrome graphs, and fault-tolerant channels.

[Fusion-based quantum computation -- Mihir Pant video](https://www.youtube.com/watch?v=E_dD1XUTaq4)  
[Fusion-based quantum computation (arxiv)](https://arxiv.org/pdf/2101.09310.pdf)  

[QIP2021 Tutorial: Architectures for fault tolerant quantum computing (Naomi Nickerson)](https://www.youtube.com/watch?v=2v-J95GFSGc)  
[Quantum Error Correction and Fault Tolerance -- Naomi Nickerson Part 1](https://www.youtube.com/watch?v=acj9dTowr90)  
[Part 2](https://www.youtube.com/watch?v=fIeZEmA8HZQ)  
[Part 3](https://www.youtube.com/watch?v=RBJ4JC-MgEA)  

[Freely Scalable Quantum Technologies Using Cells of 5-to-50 Qubits with Very Lossy and Noisy Photonic Links](https://journals.aps.org/prx/pdf/10.1103/PhysRevX.4.041041)  
[Percolation thresholds for photonic quantum computing](https://www.nature.com/articles/s41467-019-08948-x.pdf)  


>NB: These topics are way down in the implementation of "logical qubits", and the conventional wisdom is that "applications developers" need know nothing whatsoever about these details: “The system will provide you with logical qubits and logical gates operating on those logical qubits, and, e.g., the Qiskit UI won't know or care if a qubit is logical or physical -- only the error characteristics will be different.”
>
>But the core of the idea of the Seminar is to push against that conventional wisdom. Since nobody has a systematic approach to algorithm development, it seems to be a reasonable path to build quantum intuition, which I hope will carry over into algorithm development when one finally gets there.
>
>Also, the above material is an excellent physical and conceptual introduction to error correction: Surface codes and why they’re topological, stabilizer states, syndrome graphs, etc.


#### Unit 3: Analog QC and (Sometimes-Approximate) Isomorphisms to Physical Systems

Unit 3 rounds out the survey of different approaches to QC by exploring the so-called analog or adiabatic modes of quantum computer operation (e.g., what D-Wave has done).  Adiabatic quantum computing finds the ground states of Ising Hamiltonians, a set of problems that are isomorphic to the classical QUBO technique, which is in turn isomorphic to many other NP-hard problems. Here, we'll focus on the isomorphisms, and try to develop an intuition that really is in the algorithm space.  The unit will foreshadow notions of approximation that will be more fully developed in Unit 7 and Unit 8.

[Solving Quantum Chemistry Problems with a D-Wave Quantum Annealer (Sect. 2 has an overview)](https://arxiv.org/pdf/1811.05256.pdf)  
[Many other references to the basics of adiabatic QC]

In the spirit of analog optimizations to analog algorithms, we discuss a technique whereby noise is intentionally injected to enhance tunneling between successive ground states, thus achieving a reduction in the time to find the true Ising ground state.

[Noise-tolerant quantum speedups in quantum annealing without fine tuning](https://arxiv.org/pdf/1710.11056.pdf)  

We’ll also discuss the as-yet unexplored algorithmic space of triple-hybrid adiabatic QC, sequential-gate-based QC, and classical computations, which may offer advantages beyond the current hybrid schemes.
 

#### Unit 4: Some Messy Real-World Examples of Useful Solutions to Useful Problems

Unit 4 is a dive into the deep end, going through, e.g., the Will Zeng/Goldman papers and some references therein.  (There may be more/better examples.)   
[A Threshold for Quantum Advantage in Derivative Pricing](https://arxiv.org/pdf/2012.03819.pdf)  
[Low depth algorithms for quantum amplitude estimation](https://arxiv.org/pdf/2012.03348.pdf)  

>NB: The art and science of following references, and their references, until specific parts become clearer, is a skill that everyone needs to develop anyway. We can discuss this as a specific sub-unit.

The goal is to stare into the eye of the beast and realize just how daunting state-of-the-art real-world algorithms are -- and not to despair.  Emphasis is placed on the skill and intuition of finding places where the search for improvements would be most fruitful.


#### Unit 5: Hardware Technologies and Error Correction

Unit 5 extends the discussion of hardware technologies introduced in Unit 0.4, focusing on sources of error and error correction, building on the concepts developed in Unit 2.

[A Quantum Engineer’s Guide to Superconducting Qubits](https://arxiv.org/pdf/1904.06560.pdf)  
[Implementation of the XY interaction family with calibration of a single pulse](https://arxiv.org/pdf/1912.04424.pdf)  
[Efficient Z-Gates for Quantum Computing](https://arxiv.org/pdf/1612.00858.pdf)  

##### Error Correction

[Error correction overhead (Dec. 2013, theory) IBM, UCSB, USC, UC Berkeley](https://arxiv.org/pdf/1312.2316.pdf)  
[Exponential suppression of bit or phase errors with cyclic error correction (Google, Nature 2021)](https://www.nature.com/articles/s41586-021-03588-y.pdf)  
[Comparing the Overhead Of Topological and Concatenated Quantum Error Correction](https://arxiv.org/pdf/1312.2316.pdf)  

###### Recent Results in Error Correction Using Ultracold Atoms

[Logical quantum processor based on reconfigurable atom arrays](https://www.nature.com/articles/s41586-023-06927-3_reference.pdf) (Nature Accelerated Preview, Dec. 2023)
[Logical quantum processor based on reconfigurable atom arrays](https://www.nature.com/articles/s41586-023-06927-3) (Abstract; should be a more stable reference)

#### Unit 6: Quantum Memory – Uses in Algorithms and Hardware Challenges

Unit 6 introduces the concept of quantum memory, exploring its usefulness in the abstract and, drawing on hardware concepts from Unit 5, discussing real-world challenges.

[Experimental demonstration of memory-enhanced quantum communication](https://www.nature.com/articles/s41586-020-2103-5)  
[arxiv version](https://arxiv.org/pdf/1909.01323.pdf)  


#### Unit 7: Exploring Classical Techniques with an Eye Towards Developing Quantum Algorithms

Having set the stage of finding (perhaps approximate) isomorphisms between problems of interest and physical Hamiltonians in Unit 4, Unit 7 is an exploration (a sparse sampling, to be sure, but carefully curated) of classical algorithms and solution techniques to classes of interesting problems.
[This unit is largely the domain of Kyle Mandli and any other applied mathematicians who might have the needed domain expertise.]


#### Unit 8: A Brief Survey of Quantum Algorithms and Optimizations

We revisit the subject of known quantum algorithms, taking more of a middle road between the simple examples presented in Unit 0.7 and the scare tactics of Unit 4.  We focus on optimizations and improvements in algorithms, with an eye towards trying to generalize specific techniques to different classes of problems and algorithms.

[Introduction to Coding Quantum Algorithms: A Tutorial Series Using Qiskit](https://arxiv.org/pdf/1903.04359.pdf)  
[Theory of variational hybrid quantum-classical algorithms (2016)](https://iopscience.iop.org/article/10.1088/1367-2630/18/2/023023/pdf)  
[Hardware-efficient variational quantum algorithms for time evolution](https://arxiv.org/pdf/2009.12361.pdf)  
[Quantum Algorithms for Mixed Binary Optimization applied to Transaction Settlement](https://arxiv.org/pdf/1910.05788v1.pdf)  
[Accelerated Variational Quantum Eigensolver](https://arxiv.org/pdf/1802.00171.pdf)  
[Quantum Risk Analysis (arxiv June 2018, Nature Feb. 2019)](https://arxiv.org/pdf/1806.06893.pdf)  
[Nature link](https://www.nature.com/articles/s41534-019-0130-6)  
[Holographic quantum algorithms for simulating correlated spin systems (Honeywell 2020)](https://arxiv.org/pdf/2005.03023.pdf)  
[Non-Boolean Quantum Amplitude Amplification and Quantum Mean Estimation (Fermilab 2021)](https://arxiv.org/pdf/2102.04975.pdf)  
[Low depth algorithms for quantum amplitude estimation](https://arxiv.org/pdf/2012.03348.pdf)  
[Credit Risk Analysis using Quantum Computers](https://arxiv.org/pdf/1907.03044.pdf)  
[Quantum computational finance: Monte Carlo pricing of financial derivatives](https://arxiv.org/pdf/1805.00109.pdf)  
[Quantum rounding](https://arxiv.org/pdf/2108.05949.pdf)  
[Dynamic Portfolio Optimization with Real Datasets Using Quantum Processors and Quantum-Inspired Tensor Networks](https://arxiv.org/pdf/2007.00017.pdf)  
[Estimating the gradient and higher-order derivatives on quantum hardware](https://arxiv.org/pdf/2008.06517.pdf)  
[Low depth amplitude estimation on a trapped ion quantum computer](https://arxiv.org/pdf/2109.09685.pdf)


##### Linear Systems and HHL Algorithm

[Quantum algorithm for linear systems of equations (HHL 2009)](https://arxiv.org/pdf/0811.3171.pdf)  
[Quantum Circuit Design for Solving Linear Systems of Equations (2012)](https://arxiv.org/pdf/1110.2232v2.pdf)  
[Quantum linear systems algorithms: a primer (2018)](https://arxiv.org/pdf/1802.08227.pdf)  
[Variational Quantum Linear Solver](https://arxiv.org/pdf/1909.05820.pdf)  
[Qiskit Textbook Section 4.1.1](https://qiskit.org/textbook/ch-applications/hhl_tutorial.html)  


## Appendices

This section collects materials that will be made available to the students but may or may not be referenced directly in the course.  Topics and subdivisions will evolve as materials are added.

>*Note that, as of this version, the Appendix letter designations are not continuous, although they are monotonic.*


### Appendix A: Algorithms

Quantum and classical algorithms have been covered as a main part of this Course.  This Appendix lists additional references, covering perhaps a broader range of topics.


#### General Overview

The following basically-unsorted list of references on various algoritms is intended as an orientation to the literature.

[Low-Depth Mechanisms for Quantum Optimization](https://journals.aps.org/prxquantum/pdf/10.1103/PRXQuantum.2.030312)  

[Filtering variational quantum algorithms for combinatorial optimization](https://arxiv.org/pdf/2106.10055.pdf)  
[Expectation Values from the Single-Layer Quantum Approximate Optimization Algorithm on Ising Problems](https://arxiv.org/pdf/2012.03421.pdf)  
[On Quantum Computing for Mixed-Integer Programming](https://arxiv.org/pdf/2010.07852.pdf)  
[Unit Disk Graph Approximation](http://ac.informatik.uni-freiburg.de/publications/publications/dialm04.pdf)  
[Quantum Computing for Finance: State-of-the-Art and Future Prospects](https://ieeexplore.ieee.org/ielx7/8924785/8943246/09222275.pdf?tp=&arnumber=9222275&isnumber=8943246&ref=aHR0cHM6Ly9pZWVleHBsb3JlLmllZWUub3JnL2RvY3VtZW50LzkyMjIyNzU=)  
[Forecasting financial crashes with quantum computing](https://arxiv.org/pdf/1810.07690.pdf)  
[Variational quantum eigensolvers for sparse Hamiltonians](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.127.110503)  
[(arxiv version)](https://arxiv.org/pdf/2012.07171.pdf)  

[Hartree-Fock on a superconducting qubit quantum computer](https://arxiv.org/pdf/2004.04174.pdf)  
[Robustness to spontaneous emission of a variational quantum algorithm](https://arxiv.org/pdf/1910.10442.pdf)  

[Reachability Deficits in Quantum Approximate Optimization](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.124.090504)  
[A Practical Introduction to Tensor Networks: Matrix Product States and Projected Entangled Pair States](https://arxiv.org/pdf/1306.2164.pdf)

#### Quantum Fourier Techniques and Hybrid Methods for Solving PDEs

Efficient numerical PDE solvers have been an area of active research for decades.  Quantum algorithms may offer significant advantages.

[Quantum Fourier analysis for multivariate functions and applications to a class of Schrödinger-type partial differential equations](https://arxiv.org/pdf/2104.02668.pdf)

[A Quantum Algorithm for Linear PDEs Arising In Finance](https://arxiv.org/pdf/1912.02753.pdf)

#### Leveraging Quantum-Random-Cirtuit Techniques

The [Google “Quantum Supremacy”](https://www.nature.com/articles/s41586%20019%201666%205) paper (see also [Appendix X](#appendix-x)) basically used quantum random circuits to generate random vectors in a Hilbert space much more efficiently than classical algorithms can.  In <i>some</i> special cases, these random vectors can be used by quantum algorithms to solve problems more efficiently than classical algorithms.  A proof-of concept is given by Richter and Pal:

[Simulating hydrodynamics on noisy intermediate-scale quantum devices with random circuits](https://arxiv.org/pdf/2012.02795.pdf)  


##### Exploring Quantum Typicality

Since the [Richter and Pal paper above](https://arxiv.org/pdf/2012.02795.pdf) presents an algorithm that exploits random quantum circuits works efficiently because the physical system being analyzed exhibits “quantum typicality”, there may be paths to algorithms in other domains based on a generalization of quantum typicality.  In general, such studies of (exact or approximate) similarities in the mathematical structure of seemingly disparate areas is a cornerstone of our approach to algorithms development.

[Combining dynamical quantum typicality and numerical linked cluster expansions](https://arxiv.org/pdf/1901.02909.pdf)  
[Quantum Typicality and Initial Conditions](https://arxiv.org/pdf/1501.05881.pdf)  
[Enhanced Convergence of Quantum Typicality using a Randomized Low-Rank Approximation](https://arxiv.org/pdf/2102.02293.pdf)  
[Lecture 4: Quantum typicality and quantum data compression](https://www.dias.ie/wp-content/uploads/2012/06/lecture-4-wilde.pdf)

#### Classical Algorithms for Quantum Inspiration

[Hybrid Analog-Digital Solution of Nonlinear Partial Differential Equations](https://dl.acm.org/doi/pdf/10.1145/3123939.3124550)  
[(arxiv version)](https://arxiv.org/pdf/1911.00992.pdf)  

#### Quantum-Inspired Classical Algorithms

[Quantum-inspired algorithms in practice](https://arxiv.org/pdf/1905.10415.pdf)

[Quantum Solution to Classical Drag Puzzle](https://physics.aps.org/articles/pdf/10.1103/Physics.14.127)  


### Appendix B: Algorithm Verification and Testing

This Appendix covers testing.  In sound classical design (e.g., Lakos, Large-Scale C++ Software Design, Large-Scale C++ Volumes I, II, and III), software is explicitly designed for testability (which is distinct from the problem of testing).  Given the immature state of quantum algorithm development, it isn’t clear that this aspect will be relevant in the short term, but it is important to at least consider how one might test one’s programmatic ideas.

[Cross-Verification of Independent Quantum Devices](https://journals.aps.org/prx/pdf/10.1103/PhysRevX.11.031049)  


### Appendix C: Entanglement and Fundamentals

[A Delayed Choice Quantum Eraser](https://arxiv.org/pdf/quant-ph/9903047.pdf)  
[Entanglement in Graph States and its Applications](https://arxiv.org/pdf/quant-ph/0602096.pdf)  
[Long-range quantum entanglement in noisy cluster states](https://arxiv.org/pdf/quant-ph/0407255.pdf)  


### Appendix D: Decoherence (and the Quantum to Classical Transition)

Decoherence is a subject of great practical and theoretical significance.  In the main body of the Course, although we discuss entanglement and decoherence, the focus is still on an intuitive grasp of the errors, and of course the experimental error rates.  In this Appendix, we present a broader and, in some cases, more radical view of decoherence.

[Hot Buckyballs Lose Quantum Coherence](https://physicstoday.scitation.org/doi/abs/10.1063/1.1768665?journalCode=pto)  
[Decoherence of matter waves by thermal emission of radiation (Nature)](https://www.nature.com/articles/nature02276)  
[(arxiv)](https://arxiv.org/pdf/quant-ph/0402146.pdf)  

[Space from Hilbert Space: Recovering Geometry from Bulk Entanglement, S. Carroll](https://arxiv.org/pdf/1606.08444.pdf)  
[Decoherence, Einselection, And The Quantum Origins Of The Classical, W. Zurek](https://arxiv.org/pdf/quant-ph/0105127.pdf)  
[The Galileon As A Local Modification Of Gravity](https://arxiv.org/pdf/0811.2197.pdf)  
[Gravitational Dressing of 3D Conformal Galileon, G. Gabadadze](https://arxiv.org/pdf/1812.10813.pdf)  
[Time symmetry and the laws of physics](https://phys.org/news/2020-03-symmetry-laws-physics.html)  
[Decoherence of matter waves by thermal emission of radiation](https://www.nature.com/articles/nature02276)  
[Einstein-Gauss-Bonnet Gravity in Four-Dimensional Spacetime](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.124.081301)  
[Effective Field Theory Approach to Gravitationally Induced Decoherence](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.111.021302)

### Appendix E: Error Correction

This topic is covered in the main course above, but this Appendix lists additional references not expected to be covered in detail.

[The XZZX surface code](https://www.nature.com/articles/s41467-021-22274-1.pdf)
[Building a fault-tolerant quantum computer using concatenated cat codes](https://arxiv.org/pdf/2012.04108.pdf)  
[Mitiq: A software package for error mitigation on noisy quantum computers](https://arxiv.org/pdf/2009.04417.pdf)  
[Foliated Quantum Error-Correcting Codes](https://arxiv.org/pdf/1607.02579.pdf)  
[Stabilizer Codes and Quantum Error Correction](https://arxiv.org/pdf/quant-ph/9705052.pdf)  
[Dynamically protected cat-qubits: a new paradigm for universal quantum computation](https://iopscience.iop.org/article/10.1088/1367-2630/16/4/045014/pdf)  


### Appendix F: Quantum Memory

Quantum Memory is covered in its own unit above.  This Appendix lists additional references.

[Impacts of Noise and Structure on Quantum Information Encoded in a Quantum Memory](https://arxiv.org/pdf/2011.13143.pdf)  
[How Dynamical Quantum Memories Forget](https://arxiv.org/pdf/2008.10611.pdf)  
[Universal and Operational Benchmarking of Quantum Memories](https://arxiv.org/pdf/1907.02521.pdf)  
[Parametric Probabilistic Quantum Memory](https://arxiv.org/pdf/2001.04798.pdf)  
[Random-access quantum memory using chirped pulse phase encoding](https://arxiv.org/pdf/2103.11697.pdf)  
[Quantum control using quantum memory](https://arxiv.org/pdf/2009.10408.pdf)  
[A long-lived solid-state optical quantum memory for high-rate quantum repeaters](https://arxiv.org/pdf/2106.02530.pdf)  

### Appendix H: Hybrid Techniques and Systems-Level Architecture

This Appendix covers materials that are relevant to systems design.  Hybrid algorithms are covered in the main Course above.

[The theory of variational hybrid quantum-classical algorithms](https://iopscience.iop.org/article/10.1088/1367-2630/18/2/023023/pdf)  
[A quantum-classical cloud platform optimized for variational hybrid algorithms](https://arxiv.org/pdf/2001.04449.pdf)  

#### Systems

[Blueprint for a Scalable Photonic Fault-Tolerant Quantum Computer](https://arxiv.org/pdf/2010.02905.pdf)  
[IBM Quantum delivers 120x speedup of quantum workloads with Qiskit Runtime](https://research.ibm.com/blog/120x-quantum-speedup)  
[Demonstration of the trapped-ion quantum CCD computer architecture](https://arxiv.org/pdf/2003.01293.pdf)  
[Practical Quantum Computing: The value of local computation](https://arxiv.org/pdf/2009.08513.pdf)  
[Interleaving: Modular architectures for fault-tolerant photonic quantum computing](https://arxiv.org/pdf/2103.08612.pdf)  

### Appendix I: Ising Hamiltonians – D-Wave, etc.

This Appendix supplements Unit 3 and focuses on D-Wave hardware.  Additional information on the Ising Hamiltonian can be found in Appendix Q: Classical QUBO

The D-Wave approach, which they call Analog Quantum Annealing (AQA), in general, and their hardware especially, are very interesting in their own right.  A detailed study of what they’ve done is beyond the scope of this Seminar Course, but the interested reader might enjoy seeing those details.  Of some particular interest is the somewhat heated debate on the role of coherence in the performance of the D-Wave hardware.

[Mathematical Foundation of Quantum Annealing](https://arxiv.org/pdf/0806.1859.pdf)  
[What is the Computational Value of Finite Range Tunneling?](https://arxiv.org/pdf/1512.02206v1.pdf)  

[D-Wave Tutorial](https://docs.dwavesys.com/docs/latest/c_gs_1.html)

[Quantum Adiabatic Evolution Algorithms versus Simulated Annealing](https://arxiv.org/pdf/quant-ph/0201031.pdf)  
[Experimental Investigation of an Eight-Qubit Unit Cell in a Superconducting Optimization Processor](https://arxiv.org/pdf/1004.1628.pdf)  
[Architectural considerations in the design of a superconducting quantum annealing processor](https://arxiv.org/pdf/1401.5504.pdf)  
[Mediated tunable coupling of flux qubits](https://iopscience.iop.org/article/10.1088/1367-2630/7/1/230/pdf)  
[A Compound Josephson Junction Coupler for Flux Qubits With Minimal Crosstalk](https://arxiv.org/pdf/0904.3784.pdf)  
[Sign- and magnitude-tunable coupler for superconducting flux qubits](https://arxiv.org/pdf/cond-mat/0608253.pdf)  
[(PRL version]](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.98.177001)  
[Experimental Demonstration of a Robust and Scalable Flux Qubit](https://arxiv.org/pdf/0909.4321.pdf)  
[Scalable Superconducting Architecture for Adiabatic Quantum Computation](https://arxiv.org/pdf/quant-ph/0403090.pdf)  
[A scalable control system for a superconducting adiabatic quantum optimization processor](https://arxiv.org/pdf/0907.3757.pdf)  
[A scalable readout system for a superconducting adiabatic quantum optimization system](https://arxiv.org/pdf/0905.0891.pdf)  

#### Adiabatic/AQA Software
[A New Path to Create Solutions for Quantum Annealing Problems](https://www.scirp.org/pdf/jqis_2021091509415933.pdf)  

#### Adiabatic/AQA/Ising Hamiltonian and Decoherence

>tl;dr: Coherence isn’t relevant for adiabatic/AQA computations
>
>“We demonstrate that decoherence in the instantaneous energy eigenbasis does not necessarily detrimentally affect adiabatic quantum computation, and in particular that a short single-qubit T2 time need not imply adverse consequences for the success of the quantum adiabatic algorithm.”

[Decoherence in adiabatic quantum computation](https://arxiv.org/pdf/1503.08767.pdf)  
[Role of Single Qubit Decoherence Time in Adiabatic Quantum Computation](https://arxiv.org/pdf/0803.1196.pdf)  
[Entanglement in a Quantum Annealing Processor](https://journals.aps.org/prx/pdf/10.1103/PhysRevX.4.021041)
[(arxiv)](https://arxiv.org/abs/1401.3500)  
[Reexamination of the evidence for entanglement in the D-Wave processor](https://arxiv.org/abs/1506.03539)  
[Assessing the quantumness of the annealing dynamics via Leggett Garg’s inequalities: a weak measurement approach](https://www.nature.com/articles/s41598-019-50081-8.pdf)  

#### Other Hardware Approaches to AQC (or AQA, per D-Wave Terminology)

Optical Ising Model machines

[Large-scale photonic Ising machine by spatial light modulation](https://arxiv.org/pdf/1905.11548.pdf)  
[(APS Viewpoint)](https://physics.aps.org/articles/v12/61)  
[Realizing the XY Hamiltonian in polariton simulators (Vinod Menon, CCNY)](https://arxiv.org/pdf/1607.06065.pdf)  


### Appendix M: Quantum Machine Learning

Quantum Machine Learning (QML) is a large and important topic in its own right.  At present we relegate it to an appendix until we can find a way to integrate QML into the main arc of the Course.  QML will almost certainly be a “hybrid” technology integrated into an ML framework.  Of potential broader interest is the “quantum-inspired ML” section.

#### Quantum ML

[Quantum Machine Learning for Data Classification](https://physics.aps.org/articles/v14/79)  
[Continuous-variable quantum neural networks](https://arxiv.org/pdf/1806.06871.pdf)  
[Supervised learning with quantum enhanced feature spaces (June 2018)](https://arxiv.org/pdf/1804.11326.pdf)  
[Dual-Parameterized Quantum Circuit GAN Model in High Energy Physics](https://arxiv.org/pdf/2103.15470.pdf)  
[Quantum Convolutional Neural Networks](https://arxiv.org/pdf/1810.03787.pdf)  
[Quanvolutional Neural Networks: Powering Image Recognition with Quantum Circuits](https://arxiv.org/pdf/1904.04767.pdf)  
[Methods for Accelerating Geospatial Data Processing Using Quantum Computers](https://arxiv.org/pdf/2004.03079.pdf)  
[Diagrammatic Differentiation for Quantum Machine Learning](https://arxiv.org/pdf/2103.07960v1.pdf)  
[Topological Quantum Compiling with Reinforcement Learning](https://arxiv.org/pdf/2004.04743.pdf)  
[Nearest Centroid Classification on a Trapped Ion Quantum Computer](https://arxiv.org/pdf/2012.04145.pdf)  
[Information-theoretic bounds on quantum advantage in machine learning](https://arxiv.org/pdf/2101.02464.pdf)  
[Classification of MNIST dataset with Quantum Slow Feature Analysis](https://arxiv.org/pdf/1805.08837.pdf)  
[Quantum Generative Adversarial Networks for learning and loading random distributions](https://www.nature.com/articles/s41534-019-0223-2.pdf)  
[Quantum Semantic Learning by Reverse Annealing an Adiabatic Quantum Computer](https://arxiv.org/pdf/2003.11945.pdf)  
[q-means: A quantum algorithm for unsupervised machine learning](https://arxiv.org/pdf/1812.03584.pdf)  
[Power of data in quantum machine learning](https://www.nature.com/articles/s41467-021-22539-9.pdf)  

#### Quantum-Inspired Classical ML

[Quantum processor-inspired machine learning in the biomedical sciences](https://arxiv.org/ftp/arxiv/papers/1909/1909.06206.pdf)  


### Appendix N: Classical ML and Other Techniques for Improving Quantum Circuits

This topic is broad, overlapping somewhat with compilers and transpilers, hybrid techniques, error correction, and “systems architecture”.
Classical ML

[Exact and practical pattern matching for quantum circuit optimization](https://arxiv.org/pdf/1909.05270.pdf)  
[Quantum compiling by deep reinforcement learning](https://www.nature.com/articles/s42005-021-00684-3.pdf)  
[A differentiable programming method for quantum control](https://arxiv.org/pdf/2002.08376.pdf)  
[Quantum-Enhanced Data Classification with a Variational Entangled Sensor Network](https://journals.aps.org/prx/pdf/10.1103/PhysRevX.11.021047)  
[Reinforcement Learning for Digital Quantum Simulation](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.127.110502)  
[(arxiv)](https://arxiv.org/pdf/2006.16269.pdf)  
[Training Variational Quantum Algorithms Is NP-Hard](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.127.120502)  
[(arxiv)](https://arxiv.org/pdf/2101.07267.pdf)  

#### Non-ML Techniques

[Circuit quantum electrodynamics (cQED) with modular quasi-lumped models](https://arxiv.org/pdf/2103.10344.pdf)  
[Demonstrating a Continuous Set of Two-qubit Gates for Near-term Quantum Algorithms](https://arxiv.org/pdf/2001.08343.pdf)  
[(PRL version)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.125.120504)  


### Appendix Q: Classical QUBO

Quadratic Unconstrained Binary Optimization (QUBO) solves the same class of problems as AQC machines finding Ising Hamiltonian ground states.  As such, the topic is generally instructive, and a QUBO engine can be used as an efficient AQC simulator.

[Alpha-QUBO (Meta Analytics, Fred Glover)](http://meta-analytics.net/Home/AlphaQUBO)  
[Quantum Bridge Analytics I: A Tutorial on Formulating and Using QUBO Models](https://arxiv.org/ftp/arxiv/papers/1811/1811.11538.pdf)  
[Quantum Bridge Analytics II: Network Optimization and Combinatorial Chaining for Asset Exchange](https://arxiv.org/ftp/arxiv/papers/1911/1911.03036.pdf)  

#### Isomorphic Problems

[Ising formulations of many NP problems](http://arxiv.org/pdf/1302.5843.pdf)  

#### Setting up QUBO problems as Ising Hamiltonians:

[Minor-Embedding in Adiabatic Quantum Computation: I. The Parameter Setting Problem](https://arxiv.org/pdf/0804.4884.pdf)  
[Minor-embedding in adiabatic quantum computation: II. Minor-universal graph design](https://arxiv.org/pdf/1001.3116.pdf)  

### Appendix R: Rydberg Atom Systems

This topic is singled out for historic reasons (although the Appendix may expand to have subsections for other major technologies).

[Quantum Optimization for Maximum Independent Set Using Rydberg Atom Arrays](https://arxiv.org/pdf/1808.10816.pdf)  
[Generation and manipulation of Schrödinger cat states in Rydberg atom arrays](https://arxiv.org/pdf/1905.05721.pdf)  
[Parallel implementation of high-fidelity multi-qubit gates with neutral atoms](https://arxiv.org/pdf/1908.06101.pdf)  
[Rydberg mediated entanglement in a two-dimensional neutral atom qubit array](https://arxiv.org/pdf/1908.06103.pdf)  
[Pulser: An open-source package for the design of pulse sequences in programmable neutral-atom arrays](https://arxiv.org/pdf/2104.15044.pdf)  

[Accurate spectroscopy of Sr atoms](https://arxiv.org/pdf/physics/0410108.pdf)  


### Appendix T: Topological Quantum Computing

The principles of topological QC are related to the concept of quantum error correction (most of which approaches are fundamentally topological), so this Appendix is provided for whatever intuition it may engender.

[A Short Introduction to Topological Quantum Computation](
https://arxiv.org/pdf/1705.04103.pdf)  
[Mathematics of Topological Quantum Computing](
https://arxiv.org/pdf/1705.06206.pdf)  
[Introduction to topological quantum computation with non-Abelian anyons](
https://arxiv.org/pdf/1802.06176.pdf)  
[Topological Quantum Computation](
https://arxiv.org/pdf/quant-ph/0101025.pdf)  
[Topological Quantum Computing on a Conventional Quantum Computer](
https://arxiv.org/pdf/2006.05524.pdf)  
[Quantized Majorana conductance](
https://www.nature.com/articles/nature26142.pdf)  
[(arxiv version)](https://arxiv.org/ftp/arxiv/papers/1710/1710.10701.pdf)  
[Phase Signature of Topological Transition in Josephson Junctions](https://arxiv.org/pdf/1906.01179.pdf)  
[Simulating the dynamics of braiding of Majorana zero modes using an IBM quantum Computer](https://arxiv.org/pdf/2012.11660.pdf)  
[Optimizing Clifford gate generation for measurement-only topological quantum computation with Majorana zero modes](https://arxiv.org/pdf/1909.03002.pdf)  
Majorana qubits for topological quantum computing](https://physicstoday.scitation.org/doi/pdf/10.1063/PT.3.4499)  
Majorana Superconducting Qubit](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.121.267002)  
[(arxiv version)](https://arxiv.org/pdf/1803.01002.pdf)  
[Search for non-Abelian Majorana braiding statistics in superconductors](https://arxiv.org/pdf/1907.06497.pdf)  


### Appendix V: Quantum Cryptography and Communications

This subject is formally beyond the scope of this Seminar Course, but they share a common intuitive foundation.

[Coherence Equality and Communication in a Quantum Superposition](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.124.190501)  

### Appendix W: Applications Areas

This Appendix presents some representative references on applications areas.  Since each area is a major research field, the intent is not to be exhaustive, but representative.

#### Finance

[Quantum Computing In Finance – Where We Stand And Where We Could Go](https://www.science20.com/joseph_byrum/quantum_computing_in_finance_where_we_stand_and_where_we_could_go-254398)  

### <a id="appendix-x"></a> Appendix X: Quantum Complexity, Quantum Advantage, and Resource Estimation

This topic is broad and probably not well suited for a single Appendix.  Also, while complexity theory is important in the long term and is an intellectually stimulating topic, it isn’t clear that the subject has primary relevance in developing “first-to-market” algorithms and the intuition needed for shorter-term progress.  Resource estimation, on the other hand, is perhaps more relevant in the short term, and is at least partially covered in the main syllabus.  

#### Quantum Complexity

##### Scott Aaronson

[NP-complete Problems and Physical Reality](https://www.scottaaronson.com/papers/npcomplete.pdf)  
[Entanglement without end](https://www.scottaaronson.com/blog/?p=2820)  
[On the Hardness of Detecting Macroscopic Superpositions](https://arxiv.org/pdf/2009.07450.pdf)  
[Efficient Learning of Non-Interacting Fermion Distributions](https://arxiv.org/pdf/2102.10458.pdf)   (Note: As of 9/13/2021 Aaronson reports an error in this paper, actively being worked on: https://www.scottaaronson.com/blog/?p=5706)


[Landmark Computer Science Proof Cascades Through Physics and Math](https://www.quantamagazine.org/landmark-computer-science-proof-cascades-through-physics-and-math-20200304/)  
[MIP∗ = RE](https://arxiv.org/pdf/2001.04383.pdf)  
[The Universe’s Ultimate Complexity Revealed by Simple Quantum Games](https://www.quantamagazine.org/the-universes-ultimate-complexity-revealed-by-simple-quantum-games-20190305/)  

[Tsirelson’s Problem and an Embedding Theorem for Groups Arising from Non-Local Games](https://arxiv.org/pdf/1606.03140.pdf)  


#### Quantum Advantage
[Google “Quantum Supremacy”](https://www.nature.com/articles/s41586%20019%201666%205)  
[(Supplementary Information)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-019-1666-5/MediaObjects/41586_2019_1666_MOESM1_ESM.pdf)  
[(Supplemental Data)](https://datadryad.org/stash/dataset/doi:10.5061/dryad.k6t1rj8)  
[Defining and detecting quantum speedup](https://arxiv.org/pdf/1401.2910v1.pdf)  

#### Resource Estimation

[Fault-tolerant resource estimate for quantum chemical simulations: Case study on Li-ion battery electrolyte molecules](
https://arxiv.org/pdf/2104.10653.pdf)  
[Measuring the Capabilities of Quantum Computers](
https://arxiv.org/pdf/2008.11294.pdf)  
[Some Size and Structure Metrics for Quantum Software](
https://arxiv.org/pdf/2103.08815.pdf)  


### Appendix Y: Organizations, Individuals, Etc.

[The Unitary Fund](https://unitary.fund/)  
[Quantum Open Source Foundation](https://qosf.org/)  
[(Project list)](https://qosf.org/project_list/)  
[Charlie Tahan’s Meqanic quantum game](http://tahan.com/charlie/talks/2015MMquantumintuitiontalk.pdf)  
[(Meqanic app)](http://www.meqanic.com/app/)  
[Matthew Versaggi (Good approach to Intro to QC)](https://github.com/profversaggi/QuantumEducation)  
[Matt Versaggi AI](http://www.matt-versaggi.com/mit_open_courseware/  (AI))  

### Appendix Z: Esoteric Topics

[Harnessing the Power of the Second Quantum Revolution (Deutsch 2020)](https://journals.aps.org/prxquantum/pdf/10.1103/PRXQuantum.1.020101)  
[Floyd–Hoare Logic for Quantum Programs](https://dl.acm.org/doi/pdf/10.1145/2049706.2049708)  

[Variational inference with a quantum computer (CQC 2021)](https://arxiv.org/pdf/2103.06720.pdf)  

[Preparation of an exciton condensate of photons on a 53-qubit quantum computer](https://journals.aps.org/prresearch/pdf/10.1103/PhysRevResearch.2.043205)  
[(Supplemental materials)](https://journals.aps.org/prresearch/supplemental/10.1103/PhysRevResearch.2.043205/SI.pdf)  

[The Quantum Phase, Five Years After (M. V. Berry, 1988)](https://michaelberryphysics.files.wordpress.com/2013/07/berry187.pdf)  

[Accelerating lattice quantum field theory calculations via interpolator optimization using NISQ-era quantum computing](https://arxiv.org/pdf/1908.04194.pdf)  
[Grover Search as a Naturally Occurring Phenomenon](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.124.180501)  
[(arxiv version)](https://arxiv.org/pdf/1908.11213.pdf)  
[Quantum Experiments and Graphs: Multiparty States as Coherent Superpositions of Perfect Matchings](https://arxiv.org/pdf/1705.06646.pdf)  
[(PRL) (Zeilinger et al.)](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.119.240403)  
[Continuous-variable quantum computing in the quantum optical frequency comb (2019)[(https://arxiv.org/pdf/1907.09832.pdf)  

[Witnessing quantum resource conversion within deterministic quantum computation using one pure superconducting qubit](https://arxiv.org/pdf/1806.05543.pdf)  
[Eigenvectors from eigenvalues: a survey of a basic identity in linear algebra](https://arxiv.org/pdf/1908.03795.pdf)  
[Eigenvalues: the Rosetta Stone for Neutrino Oscillations in Matter](https://arxiv.org/pdf/1907.02534.pdf)  
[Orthogonality Catastrophe as a Consequence of the Quantum Speed Limit](https://arxiv.org/pdf/1910.10728.pdf)  
[Black holes in the quantum universe](https://arxiv.org/pdf/1905.08807.pdf)  
[Quantum Mechanics can be understood through stochastic optimization on spacetimes](https://www.nature.com/articles/s41598-019-56357-3.pdf)  
[A two-qubit engine fueled by entangling operations and local measurements](https://arxiv.org/pdf/2007.03239.pdf)  
[Democratizing Spin Qubits](https://arxiv.org/pdf/2001.08251.pdf

[Topological limits to the parallel processing capability of network architectures](https://www.nature.com/articles/s41567-021-01170-x)  

[Quantum Theory Cannot Violate a Causal Inequality](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.127.110402)  
[(arxiv version)](https://arxiv.org/pdf/2101.09107.pdf)


