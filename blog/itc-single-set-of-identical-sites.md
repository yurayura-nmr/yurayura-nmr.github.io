
### 2. **Binding Equations (Single Set of Identical Sites)**

#### **Parameter Key**
- $$ K $$: binding constant
- $$ n $$: number of binding sites per macromolecule
- $$ M_t $$: bulk macromolecule concentration after correction
- $$ X_t $$: corrected ligand concentration
- $$ [M] $$: free macromolecule concentration inside cell
- $$ [X] $$: free ligand concentration inside cell
- $$ \theta $$: fractional occupancy (fraction of sites occupied)
- $$ \Delta H $$: enthalpy per mole binding

#### **Key Equations**

**a. Binding Isotherm:**
$$
K = \frac{\theta}{(1-\theta)[X]}  \tag{5}
$$

**b. Ligand Mass Balance:**
$$
X_t = [X] + n\theta M_t  \tag{6}
$$
(The total ligand in the cell = free + bound ligand)

**c. Rearranged (Quadratic) Equation for $$ \theta $$:**
$$
\theta^2 - \theta \left[ \frac{1 + X_t / (n M_t) + 1/(n K M_t)}{1} \right] + \frac{X_t / (n M_t)}{1} = 0  \tag{7}
$$

This quadratic must be solved for $$ \theta $$ at each injection point.

***

### 3. **Heat Content Calculation**

The total heat after each injection, for the “single set of sites” model:

$$
Q = n \theta M_t \Delta H V_0  \tag{8}
$$

Solving the quadratic for $$ \theta $$ and using in heat equation:

$$
Q = \frac{n M_t \Delta H V_0}{2} \left[1 + \frac{X_t}{n M_t} + \frac{1}{n K M_t} - \sqrt{\left(1 + \frac{X_t}{n M_t} + \frac{1}{n K M_t}\right)^2 - 4 \frac{X_t}{n M_t}} \right]  \tag{9}
$$

***

### 4. **Takeaways for Data Fitting**

- For each injection, correct both $$ M_t $$ and $$ X_t $$ using the “dilution” factor as above.
- Calculate the total heat ($$ Q $$) for each point using equations (8) or (9).
- Fit model parameters ($$ K $$, $$ n $$, $$ \Delta H $$) to experimental heats by minimizing the difference between measured and predicted $$ Q $$.
- These calculations are the basis for all “one set of identical sites” ITC fitting models in software such as Origin.

***

Here’s the next section, formatted for clear reference and direct pasting into your `ITC-faq.md`. This covers the calculation of the heat per injection and the rationale for the displaced volume correction.

***

## Calculating Injection Heats With Displaced Volume Correction ([MicroCal ITC Manual, Appendix A])[1]

At each step in ITC data analysis, the fitted heat is not simply the difference $$ Q(i) - Q(i-1) $$ between “total heat content” after two consecutive injections—a correction must be made for the fact that a fraction of the solution in the active cell is displaced and replaced with each injection.

### 1. **Why Correct for Displaced Volume?**

- The formula for total heat content, $$ Q(i) $$, only applies to the solution *currently* in the active cell volume ($$ V_0 $$), after the $$ i $$-th injection.
- Each injection of volume $$ \Delta V_i $$ means some of the solution (and associated enthalpy) that was in the cell after the $$ (i-1) $$-th injection is now displaced into the inactive (upper) tube.
- Although this displaced solution is no longer being measured after the injection, it still participated in binding and contributed to the measured heat during the mixing/kinetics phase. Experimental data shows that about **half** the heat effect from a given injected increment is actually contributed by the displaced portion.

### 2. **Corrected Incremental Heat Equation**

Therefore, the **actual heat** to use for model comparison with the raw data for the $$ i $$-th injection is:

$$
\Delta Q(i) = Q(i) + \frac{\Delta V_i}{2V_0} [Q(i) + Q(i-1)] - Q(i-1)  \tag{10}
$$

- $$ Q(i) $$: total heat content after $$ i $$-th injection, calculated from isotherm model  
- $$ Q(i-1) $$: total heat content after previous injection  
- $$ \Delta V_i $$: volume of the $$ i $$-th injection  
- $$ V_0 $$: working (active) volume of the cell

This accounts for:
- The difference in heat capacities after and before the injection
- The partial (50%) effect of the displaced solution.

This correction is essential for accurate fit, especially for larger injection volumes.

***

### 3. **Model Fitting: Steps Involved**

Fitting an ITC isotherm to experimental data involves these main steps:

1. **Initial Parameter Guess**
   - Guess values for number of sites ($$ n $$), binding constant ($$ K $$), and enthalpy ($$ \Delta H $$), typically provided by the fitting software.
2. **Calculate $$ \Delta Q(i) $$** for Each Injection
   - For each injection, use parameter guesses and the above equation to predict the heat released per injection.
3. **Compare With Experimental Heats**
   - Assess how well the predicted $$ \Delta Q(i) $$ values match the actually observed heats.
4. **Iterate by Parameter Optimization**
   - Adjust $$ n $$, $$ K $$, and $$ \Delta H $$ using a minimization algorithm (most commonly Marquardt-Levenberg nonlinear least squares) to improve fit iteratively.
5. **Conclude When Fit Is Optimal**
   - Continue until no significant improvement in fit occurs.

***

#### References

- MicroCal iTC200 System Manual, Appendix A[1]

***

