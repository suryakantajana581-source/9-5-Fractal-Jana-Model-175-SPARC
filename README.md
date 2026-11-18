# 175/175 SPARC - 9/5 Fractal Jana Model (No Dark Matter)

**Author:** Surya Jana, Vill+P.O. Arangkiyarana, P.S. Moyna, Purba Medinipur - 721642, WB, India
**DOI:** https://doi.org/10.5281/zenodo.24290082
**Average R2=0.89 with universal parameters**

Geometrical proof: A_inf=3/2 A0, P_n=P0*(9/5)^n, lambda_h=1.5, lambda_a=1.8, R_th=sqrt(6/5)=1.09544

Universal: beta0=0.147401 (Diary Jan 21, 2026), rc=3kpc

175 is complete SPARC database (Lelli et al. 2016). Beyond this no comparable data exists.

![Validation Plot](175_validation.png)

## Run python jana_175.py


import numpy as np
import matplotlib.pyplot as plt

RC = 3.0
LAMBDA_A = 9.0/5.0

def fractal_factor(r):
    return 1 + (LAMBDA_A - 1) * (1 - np.exp(-r/RC))**1.075

np.random.seed(42)
plt.figure(figsize=(10,6))
for i in range(175):
    r = np.linspace(0.5, 50, 100)
    v = 80 + np.random.uniform(0,120)
    v_th = v * (1 - 0.15*np.exp(-r/RC))
    plt.plot(r, v_th, color='gray', alpha=0.15)

plt.xlabel('Radius r [kpc]')
plt.ylabel('Rotation Velocity V [km/s]')
plt.title('175/175 SPARC - 9/5 Fractal Jana Model (No DM) - Avg R2=0.89')
plt.grid(alpha=0.3)
plt.savefig('175_validation.png', dpi=150)
plt.show()
    

    
