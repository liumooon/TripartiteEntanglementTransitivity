# Generic Tripartite Entanglement Transitivity 

Matlab data relevant to **Table II** in the preprint [Large Parts are Generically Entangled Across All Cuts](https://iopscience.iop.org/article/10.1088/2058-9565/ae30a4/pdf). 

*(Note: these files are not the exact dataset used to produce Table II. They are generated using the same code and exhibit similar category ratios.)*

For each dimension triple $(d_A,d_B,d_C)$ not covered by **Theorem 4**, we generate 500 Haar-random pure tripartite states. 
For example, for $d_A=2,d_B=4,d_C=2$, the output is saved as `A2_B4_C2.mat`. 

## File contents

Each `.mat` file contains three cell arrays, where the $i$-th row for each corresponds to the $i$-th sample:

- `SampledStates`: the generated Haar-random pure state, which is a $d_Ad_Bd_C \times 1$ vector.
- `Fidelity`: the fidelity $\mathcal{F}$ between the generated state and the optimized compatible state obtained via the SDP mentioned in **Appendix G**.
  In the data provided here, one observes that $1-\mathcal{F} < 10^{-6}$.
This indicates that, within numerical precision of the optimization, the global state is uniquely determined by the marginals $\rho_{AB}$ and $\rho_{BC}$.
- `Category`: an integer index ranging from 1 to 8 specifying the marginal entanglement category of the generated state, determined by the PPT criterion applied to $(\rho_{AB},\rho_{BC},\rho_{AC})$.
The ordering matches that in **Table II**: NNN, NPN, PNN, PPN, NNP, NPP, PNP, PPP.
For instance, a state whose marginals $\rho_{AB}, \rho_{BC}$ are NPPT while $\rho_{AC}$ is PPT falls in the category of NNP.
