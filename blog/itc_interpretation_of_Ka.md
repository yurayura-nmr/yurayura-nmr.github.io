
## Derivation of How $$Ka$$ Is Related to the Slope of $$ \theta $$

### Step 1: Start with the quadratic equation for occupancy:

$$
\theta = \frac{1}{2} \left[ 1 + \frac{X_t}{n M_t} + \frac{1}{c} - \sqrt{\left(1 + \frac{X_t}{n M_t} + \frac{1}{c}\right)^2 - 4 \frac{X_t}{n M_t}} \right]
$$

where:

- $$ c = n \times K \times M_t $$

### Step 2: Focus on the inflection point:

At the point of maximum slope (around the midpoint where $$ \theta \approx 0.5 $$), the **derivative**:

$$
\frac{d\theta}{dX_t}
$$

controls the shape.

### Step 3: Simplify to identify dependence on $$ c $$:

Define:

$$
A = 1 + \frac{X_t}{n M_t} + \frac{1}{c}
$$
$$
D = \sqrt{A^2 - 4 \frac{X_t}{n M_t}}
$$

Thus:

$$
\theta = \frac{1}{2} (A - D)
$$

### Step 4: Derivative of $$ \theta $$:

$$
\frac{d\theta}{dX_t} = \frac{1}{2} \left( \frac{dA}{dX_t} - \frac{dD}{dX_t} \right)
$$

$$
\frac{dA}{dX_t} = \frac{1}{n M_t}
$$

and,

$$
\frac{dD}{dX_t} = \frac{1}{2} \times \frac{2A \frac{dA}{dX_t} - 4 \times \frac{1}{n M_t}}{D}
$$
$$
= \frac{A \frac{1}{n M_t} - 2 \times \frac{1}{n M_t}}{D} = \frac{\frac{A - 2}{n M_t}}{D}
$$

Putting it all together:

$$
\frac{d\theta}{dX_t} = \frac{1}{2} \left( \frac{1}{n M_t} - \frac{\frac{A - 2}{n M_t}}{D} \right)
$$
$$
= \frac{1}{2 n M_t} \left( 1 - \frac{A - 2}{D} \right)
$$

***

## Step 5: Connect $$ c $$ to $$ Ka $$

- At the **midpoint of the sigmoid** where $$ \theta \approx 0.5 $$:

$$
A \approx 1 + \frac{X_t}{n M_t} + \frac{1}{c}
$$

- When the ratio $$ \frac{X_t}{n M_t} $$ is close to 1 (the molar ratio at the midpoint), the maximum slope is approximately:

$$
\left. \frac{d\theta}{dX_t} \right|_{\text{midpoint}} \sim \frac{1}{2 n M_t} \times \frac{c/2}{A} \sim \frac{1}{2 n M_t} \times \frac{c}{A}
$$

Given $$ c = n K_a M_t $$, this simplifies to:

$$
\text{Max slope} \propto \frac{K_a}{A}
$$

- Because $$A$$ is roughly proportional to $$c$$, the **steepness** of the sigmoid **scales with $$K_a$$** directly:

$$
\text{Steepness} \sim \frac{1}{(1 + c)} \times c
$$

- When $$ c \gg 1 $$, the slope approaches $$ \sim c $$, proportional to $$ K_a $$.

***

## **Conclusion:**

- **Mathematically, the slope of $$ \theta $$ at the midpoint (inflection point) is proportional to $$ K_a $$.**
- Explicitly: **max $$ d\theta/dX_t $$ ≈ proportional to $$ n \times K_a $$**, especially when $$ c $$ is large.

***

This derivation explicitly shows how $$ K_a $$ impacts the slope mathematically, with the steepness increasing with higher affinity (larger $$ K_a $$).

[7](https://digital.csic.es/bitstream/10261/237597/1/Isothermal%20Titration.pdf)
[8](https://www.sciencedirect.com/science/article/abs/pii/S0003269723004116)
[9](https://www.nature.com/articles/s41467-018-03263-3)
