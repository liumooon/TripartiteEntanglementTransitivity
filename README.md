# Generic Tripartite Entanglement Transitivity 

Matlab data relevant **Table II** in the preprint [Large Parts are Generically Entangled Across All Cuts](https://iopscience.iop.org/article/10.1088/2058-9565/ae30a4/pdf). 

For each dimension triple $(d_A,d_B,d_C)$ not covered by the regime considered in **Theorem 4**, we generate 500 Haar-random pure tripartite states. 
In the case of $d_A=2,d_B=4,d_C=2$, for example, the output is saved in file `A2_B4_C2.mat`. 

The states are further classified into 8 categories `catXYZ` by their marginal entanglement, using the PPT criterio.
The three letters XYZ record the marginal entanglement status in the order of $(AB,BC,AC)$.
For instance, a state whose marginals $\rho_{AB}, \rho_{BC}$ are NPPT while $\rho_{AC}$ is PPT is stored in `catNNP`.

Each `catXYZ` is a cell array with three columns:
- `catXYZ{i,1}`: the $i$-th generated state
- `catXYZ{i,1}`: the $i$-th optimized compatible state
- `catXYZ{i,3}`: the fidelity $\mathcal{F}$ between the generated state and the optimized compatible state returned by the SDP described in **Appendix G** in the paper.

In the data provided here, one observes that $1-\mathcal{F} < 10^{-6}$.
This indicates that, within numerical precision of the optimization, the global state is uniquely determined by the marginals $\rho_{AB}$ and $\rho_{BC}$.

Finally, in each data file, we also provide the ratio of each category, which is listed in the same order as **Table II**.
