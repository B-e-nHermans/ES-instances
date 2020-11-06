# Instances and computational results for the paper ``Exact and approximation algorithms for the expanding search problem'' by Ben Hermans, Roel Leus, and Jannik Matuschke

The folder `instances' describes the generated instances used for the computational experiments in Section 5 of the paper;
The folder `results' contains the computational results for the individual instances, the averaging of which led to Tables 1-2 and Figure 4 in the paper.

The different (sub)folders and the structure of the contained files are described in more detail below.



## instances

* coordinates: 
	In file `coordinates_nA_repB.dat', row i gives the x-, y-, and z-coordinate of vertex i for 
	the Bth repetition of an instance with n = A non-root vertices (where row 0 corresponds to the root).
* graph_structure: 
	In file `adjacency_matrix_nA_repB.dat', matrix element (i,j) gives a number such that if this number is 
	smaller than or equal to the number of edges, then edge {i,j} is included in the graph for the Bth repetition 
	of an instance with n = A non-root vertices (where row and column 0 correspond to the root). The number of edges
	to be included is then determined by the density one wants to obtain. 
* probs:
	In file `probabilities_nA_repB.dat', row i gives the probability that vertex i contains the object for 
	the Bth repetition of an instance with n = A non-root vertices (where row 0 corresponds to the root).

Please note that the instances for the paper
	``Averbakh I, Pereira J (2012) The flowtime network construction problem. IIE Transactions 44(8):681-694.''
are not included in this folder, but can be obtained via the repository https://github.com/jordipereiragude/flowtimenetworkconstructioninstances



## results

* bounds:
	These files give the computational results used to construct Figure 4 in the paper.
	In file `nX_dY.dat', row i gives for repetition i of the instances with n = X non-root vertices and density Y the following results:
	* n: the number of non-root vertices
	* dens: the graph's density
	* rep: the repetition identifier
	* LPR0: the objective function value for the LP-relaxation when no cuts are included
	* LPR1: the objective function value for the LP-relaxation when only including cuts C1
	* LPR2: the objective function value for the LP-relaxation when only including cuts C2
	* LPR3: the objective function value for the LP-relaxation when including both cuts C1 and C2
	* G: the objective function value obtained by the greedy heuristic
	* LS: the objective function value obtained by the local search heuristic
	* optVal: the optimal objective function value

* influence_network_density: 
	These files give the computational results used to construct Table 2 in the paper.
	In file `MIP011_nX_dY.dat', row i gives for repetition i of the instances with n = X non-root vertices and density Y the following results:
	* n: the number of non-root vertices
	* rep: the repetition identifier
	* time: CPU time in seconds needed to solve the instance (with time limit of 1200 seconds)
	* value: objective function value of the best found solution within the time limit of 1200 seconds
	* gap: optimality gap; only non-zero if time limit is reached
	* LPvalue: objective function value of LP relaxation with all cuts included
	* H0: the objective function value obtained by the greedy heuristic
	* H1: the objective function value obtained by the local search heuristic

* output_Averbakh_Pereira_2012:
	These files give the computational results used to construct Table 1 in the paper.
	In file `AP_nX_Y_Z.dat',
		* the quantity X indicates the number of vertices (including the root);
		* Y \in {eucl, rand} indicates whether the network structure is Euclidean or random, respectively;
		* Z \in {u, w} indicates whether the vertices are unweighted or weighted, respectively.
	Row i in each file gives for repetition i the following results:
	* n: the number of non-root vertices
	* rep: the repetition identifier
	* time: CPU time in seconds needed to solve the instance (with time limit of 1200 seconds)
	* value: objective function value of the best found solution within the time limit of 1200 seconds
	* gap: optimality gap; only non-zero if time limit is reached
	* LPvalue: objective function value of LP relaxation with all cuts included
	* H0: the objective function value obtained by the greedy heuristic
	* H1: the objective function value obtained by the local search heuristic