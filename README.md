# Generic Tripartite Entanglement Transitivity 

Matlab data relevant to **Table II** in the preprint [Large Parts are Generically Entangled Across All Cuts](https://iopscience.iop.org/article/10.1088/2058-9565/ae30a4/pdf). 

For each dimension triple $(d_A,d_B,d_C)$ not covered by **Theorem 4**, we generate 1000 Haar-random pure tripartite states. 
In the case of $d_A=2,d_B=4,d_C=2$, for example, the output is saved in file `A2_B4_C2.mat`. 

In each data file, one finds a cell `Data` with 4 columns.
- `Data{i,1}`: The $i$-th generated Haar-random pure state.
- `Data{i,2}`: The $i$-th optimized compatible state returned by the SDP described in **Appendix G** in the paper.
- `Data{i,3}`: The fidelity $\mathcal{F}$ between the generated state and the optimized compatible state. In the data provided here, one observes that $1-\mathcal{F} < 10^{-6}$.
This indicates that, within numerical precision of the optimization, the global state is uniquely determined by the marginals $\rho_{AB}$ and $\rho_{BC}$.
- `Data{i,4}`: an integer index ranging from 1 to 8 indicating the 8 marginal entanglement categories that the state belongs to. The order of the indices is exactly the same in **Table II**: NNN, NPN, PNN, PPN, NNP, NPP, PNP, PPP. For instance, a state whose marginals $\rho_{AB}, \rho_{BC}$ are NPPT while $\rho_{AC}$ is PPT falls in the category of NNP.
