## ITC Data Analysis: Key Equations and Steps (Single Set of Identical Sites)

### Parameter Key

- K: binding constant  
- n: number of binding sites per macromolecule  
- Mt: macromolecule concentration after volume correction  
- Xt: ligand concentration after volume correction  
- [M]: free macromolecule concentration in the cell  
- [X]: free ligand concentration in the cell  
- theta: fraction of binding sites occupied  
- dH: enthalpy (heat change) per mole of binding  
- V0: working (active) volume of the cell  

***

### Main Binding Equations

a. **Binding Isotherm Relation**  
K = theta / ((1 - theta) * [X])    (Equation 5)

b. **Ligand Mass Balance**  
Xt = [X] + n * theta * Mt          (Equation 6)  
(The total ligand in the cell is the free ligand plus the ligand bound to sites.)

c. **Quadratic Equation for theta**  
theta^2 - theta * (1 + Xt / (n * Mt) + 1/(n * K * Mt)) + (Xt / (n * Mt)) = 0   (Equation 7)

You need to solve this quadratic equation for theta at each injection point.

***

### Heat Content Calculations

- The total heat after each injection for a single set of sites model is:  
Q = n * theta * Mt * dH * V0      (Equation 8)

- Alternatively (using the full quadratic result for theta):  
Q = (n * Mt * dH * V0 / 2) *  
    [1 + Xt / (n * Mt) + 1/(n * K * Mt) -  
      sqrt((1 + Xt / (n * Mt) + 1/(n * K * Mt))^2 - 4 * Xt / (n * Mt))]     (Equation 9)  

***

### Concentration Corrections for Displaced Volume

For each injection, both macromolecule and ligand concentrations in the cell (Mt and Xt) should be corrected for the fact that an injection displaces some of the cell volume. For any cumulative volume injected (Delta V), the correction for the concentration after a number of injections is:

Corrected concentration = starting concentration * 2*V0 / (2*V0 + Delta V)

Apply this both to Mt and Xt before using the values above in the binding equations.

***

### Calculating the Heat for Each Injection (Displaced Volume Correction)

After calculating the total heat as above, you need to compute the **incremental heat**—that is, the heat released during each injection, which is what you directly compare with experimental data.  
This is NOT just Q(i) - Q(i-1). You need to also correct for the fact that each injection pushes some solution out of the active cell (but the displaced solution still contributes about half the heat expected from remaining in the cell):

Delta Q(i) = Q(i) + (Delta V_i / 2V0) * (Q(i) + Q(i-1)) - Q(i-1)     (Equation 10)

Where:  
- Q(i) = total cell heat after the i-th injection  
- Q(i-1) = total after the previous injection  
- Delta V_i = the injection volume for injection i  
- V0 = working cell volume

***

### Steps for Model Fitting

1. Make initial guesses for n, K, and dH (typically the fitting software supplies these).
2. For each injection, correct macromolecule and ligand concentrations and use them (with your trial parameters) to calculate heat per injection as above.
3. Compare the calculated heat (Delta Q(i)) with the experimentally observed heat.
4. Adjust n, K, and dH iteratively using minimization (e.g., Marquardt-Levenberg) until there is no further significant improvement in fit.

***

| Parameter        | Meaning / Role                                           | Typical Usage Context                     | Notes / Interpretation                                                  |
|------------------|---------------------------------------------------------|-------------------------------------------|-------------------------------------------------------------------------|
| **n (small n)**  | Number of binding sites per macromolecule                | Classical ITC equations and theory        | True molecular binding sites; may reflect active fraction if < 1       |
| **N (capital N)**| Binding stoichiometry or effective molar ratio          | Origin and many fitting software outputs  | Includes effects of concentration errors and active/inactive species; often fit parameter rather than fixed value |
| **inc.B** (incompetent fraction B) | Fraction of ligand or macromolecule that is inactive or incapable of binding | SEDPHAT-GUSSI global analysis framework  | Explicit modeling of inactive fractions; constrained between 0 and 1; used in concentration corrections and global fitting |

***

### Additional Notes:

- **n** is the theoretical or actual number of ligand binding sites on a single macromolecule molecule.
- **N** in software like Origin often reflects *effective* stoichiometry, combining true site number with sample activity and concentration accuracy.
- **inc.B** or incompetent fractions represent species in the sample that do not participate in binding (e.g., misfolded protein, degraded ligand), improving fit quality and realism in global analyses.
- When interpreting ITC data, distinguish clearly whether stoichiometry refers to true molecular sites, effective stoichiometry in fits, or explicit inactive fractions.

***
