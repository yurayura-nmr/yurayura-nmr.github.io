
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
