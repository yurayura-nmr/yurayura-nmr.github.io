## Derivation Showing ΔH Represents Total Heat Drawdown in ITC

1. **Heat per Injection and ΔH**

From the binding model equations, the total heat content after the i-th injection is:

Q(i) = n * θ * Mt * ΔH * V0

- $$ n $$ = number of binding sites per macromolecule  
- $$ θ $$ = fraction of occupied sites  
- $$ Mt $$ = macromolecule concentration corrected for displaced volume  
- $$ ΔH $$ = enthalpy change per mole of ligand binding  
- $$ V_0 $$ = active cell volume  

This shows that the **heat produced or absorbed at any point is proportional to ΔH**, scaled by how many binding sites are occupied.

2. **Integrated Thermogram and Total ΔH**

The entire thermogram integrates the heat released across all injections—from zero binding to saturation.

- At the start, $$ θ = 0 $$ (no ligand bound), heat is zero relative to baseline.
- At full saturation, $$ θ \approx 1 $$, so the total heat reaches approximately:  
  $$ Q_{total} \approx n * Mt * ΔH * V_0 $$.

Thus, the **total integrated heat change corresponds to the full saturation of all binding sites, multiplied by ΔH**.

3. **Graphical Interpretation**

- The **vertical height or total cumulative heat change** of the ITC binding isotherm curve (area under heat peaks) reflects the **magnitude of ΔH** scaled by $$ n $$ and $$ Mt $$.
- By fitting the model to experimental heats, ΔH is extracted as the enthalpy per binding event that best explains total heat release.
- This is why ΔH correlates directly with the **total “drawdown” or “updraw”** in integrated heat, seen visually on thermogram plots.

***

### Summary

The fundamental ITC binding heat equation literally expresses heat as the product of ΔH, number of sites $$ n $$, and occupied sites fraction $$ θ $$. Integrating over the entire titration, the total heat equals the total number of binding events times ΔH. Hence, ΔH determines the vertical scale or total energy change displayed by the ITC thermogram.

***


