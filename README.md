# Generic Tripartite Entanglement Transitivity in Unproven Dimension Regions

Matlab data relevant to **Table II** in the preprint [Large Parts are Generically Entangled Across All Cuts](https://iopscience.iop.org/article/10.1088/2058-9565/ae30a4/pdf). 

*(Note: these files are not the dataset used to produce Table II, but were generated subsequently with more samples using the same code, showing similar category ratios.)*

For each dimension triple $(d_A,d_B,d_C)$ not covered by **Theorem 4**, we generate 5000 Haar-random pure tripartite states. 
For example, for $d_A=2,d_B=4,d_C=2$, the output is saved as `A2_B4_C2_5kTrials_Data.mat`. 

## File contents

Each `.mat` file contains five variables as explained below:

- `d`: A $1\times3$ vector $[d_A$ $d_B$ $d_C]$ specifying the local dimensions of the Hilbert space concerned.
- `SampledStates`: A $(d_Ad_Bd_C)\times 5000$ matrix where the $i$-th column gives the $i$-th sampled Haar-random pure state, which is a $d_Ad_Bd_C \times 1$ vector.
- `Fidelity`: A vector whose $i$-entry gives the fidelity $\mathcal{F}$ between the $i$-th generated state, `SampledStates`(:,i), and the optimized compatible state obtained via the SDP mentioned in **Appendix G**.
  In the data provided here, one observes that $1-\mathcal{F}$ is of the order of $10^{-6}$.
This indicates that, within numerical precision of the optimization, the global state is uniquely determined by the marginals $\rho_{AB}$ and $\rho_{BC}$.
- `Lambda`: A matrix whose $i$-th row  gives the smallest eigenvalue of the partial transposition of the marginals $\rho_{AB}$, $\rho_{BC}$, and $\rho_{AC}$, respectively, where $\rho_{ABC}=$`SampledStates`(:,i)*`SampledStates`(:,i).
- `Category`: A vector whose $i$-entry gives an integer index ranging from 1 to 8 specifying the marginal entanglement category of the generated state, determined by the PPT criterion applied to $(\rho_{AB},\rho_{BC},\rho_{AC})$.
The ordering matches that in **Table II**: NNN, NPN, PNN, PPN, NNP, NPP, PNP, PPP.
For instance, a state whose marginals $\rho_{AB}, \rho_{BC}$ are NPPT while $\rho_{AC}$ is PPT falls in the category of NNP.
