## ITC Working Volume and Concentration Correction (from MicroCal Manual, Appendix A)

At the start of an ITC experiment, both the active cell and the long communication tube are filled with macromolecule (typically the protein) solution. Only the solution within the **working (active) volume** of the cell, $$ V_0 $$, is sensed calorimetrically. The communication tube above the active volume is considered inactive in the measurement.

### Volume Definitions

- $$ V_0 $$: working (active) volume of the cell  
- $$ \Delta V_i $$: volume added by the *i-th* injection  
- $$ \Delta V $$: cumulative total injected volume at any given time  
  $$
  \Delta V = \sum_i \Delta V_i
  $$

Because the cell is completely filled, each injection displaces an equivalent volume of liquid from the working region into the inactive tube. Hence, the solution actually "sensed" by the calorimeter changes slightly in composition as injections proceed.

### Concentration Change with Injection

Initially, the cell contains macromolecule at concentration $$ M_0 $$ in volume $$ V_0 $$. After cumulative injections totaling $$ \Delta V $$, the macromolecule originally in $$ V_0 $$ is now distributed across a slightly larger total volume $$ V_0 + \Delta V $$.

The instantaneous (current) concentration of the macromolecule in the active cell after injection *t* is denoted $$ M_t $$.

The **bulk concentration** of macromolecule displaced into the inactive tube by each injection ($$ \Delta V $$) is approximately the average of the concentration before and after injection:

$$
M_{\text{avg}} = \frac{M_{t-1} + M_t}{2}
$$

### Conservation of Mass

Mass conservation implies that the total moles of macromolecule initially in the active volume remains constant:

$$
M_0 V_0 = M_t V_0 + M_{\text{avg}} \Delta V
$$

Substituting $$ M_{\text{avg}} = \frac{M_{t-1} + M_t}{2} $$ and solving for $$ M_t $$ gives the recursive relation used for cell concentration correction in ITC data processing.

This correction is implemented automatically in MicroCal’s data analysis software but is important to understand conceptually: each injection slightly dilutes the macromolecule sample in the measured cell volume.

***

