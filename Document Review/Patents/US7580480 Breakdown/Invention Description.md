
## 4:22-36
# Conditional Probability Vector

The referenced text describes the process of calculating the **conditional probability vector** in the context of **soft decision demodulation** for a **square QAM signal constellation**. Here is the breakdown:

#### First Half Bits vs. Second Half Bits
- **First half bits**: Determined by one signal component (real part, α).
- **Second half bits**: Determined by the other signal component (imaginary part, β).

#### Conditional Probability Vector
- Represents the likelihood of each bit value (0 or 1) based on the received signal components, accounting for the effects of noise.
- Used in soft decision decoding to provide probabilistic information about each bit.

### Process of Calculating Conditional Probability Vector

#### First Half Bits

1. **Focus on Real Component (α):**
   - Extract the real part (α) of the received signal.
   - Compare α to the expected constellation points along the real axis.

2. **Gaussian Probability Model:**
   - The likelihood that α corresponds to a specific level is given by:
     
$$
P(\alpha | \text{level}) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(\alpha - \text{level})^2}{2\sigma^2}\right)
$$

3. **Normalize Probabilities:**
   - Calculate probabilities for all possible levels.
   - Normalize them to ensure they sum to 1.

#### Second Half Bits
1. Focus on Imaginary Component (β), extract the imaginary part (β) of the received signal.
3. Repeat the same process as for the first half bits but using the β values and the corresponding constellation points on the imaginary axis.

### **3. Example Calculation Using Fig. 2, Fig. 3, and Fig. 4**

#### Given:
- **Received signal**: y = 1.8 + j1.8.
- **Noise variance (σ²)**: 0.5.
- **Constellation points (16-QAM):**
  - Real axis (α): \[-3, -1, 1, 3\].
  - Imaginary axis (β): \[-3, -1, 1, 3\].

#### **First Half Bits (Determined by $\alpha$):**
1. **Compute Squared Distances:**
   - For $\alpha = 1.8$:
     - Distance to -3: $(1.8 - (-3))^2 = 22.09$.
     - Distance to -1: $(1.8 - (-1))^2 = 7.84$.
     - Distance to 1:  $(1.8 - 1)^2 = 0.64$.
     - Distance to 3:  $(1.8 - 3)^2 = 1.44$.

2. **Compute Exponentials:**
   - Using the Gaussian model with $\alpha^2 = 0.5$:
	- $P(\alpha \mid -3) \approx 0$
	- $P(\alpha \mid -1) \approx 0$
	- $P(\alpha \mid -1) \approx 0.298$
	- $P(\alpha \mid 3) \approx 0.274$

3. **Normalize:**

   $$
   \begin{gather}
   P_{\text{total}} = 0 + 0 + 0.298 + 0.274 = 0.572 \\
   P(b_0b_1 = 11) = \frac{0.298}{0.572} \approx 0.521 \\
   P(b_0b_1 = 10) = $\frac{0.274}{0.572} \approx 0.479
   \end{gather}
   $$

4. **Result for First Half Bits:**
   - Conditional probability vector: $P(b_0b_1 = 11), P(b_0b_1 = 10) \approx [0.521, 0.479]$.

#### **Second Half Bits (Determined by $\beta$):**
Repeat the same steps for $\beta = 1.8$ (imaginary part), yielding:
- Conditional probability vector: $P(b_2b_3 = 11), P(b_2b_3 = 10) \approx [0.521, 0.479]$.

#### **Conversion to LLRs:**
The conditional probability vectors can be converted to Log-Likelihood Ratios (LLRs) using:

$$
\text{LLR}(b_k) = \ln\left(\frac{P(b_k = 0 | y)}{P(b_k = 1 | y)}\right)
$$

#### Example for b₀

From the first half:
- $P(b_0 = 0) = P(b_0b_1 = 10) = 0.479$.
- $P(b_0 = 1) = P(b_0b_1 = 11) = 0.521$

LLR:
$$
\text{LLR}(b_0) = \ln\left(\frac{0.479}{0.521}\right) = \ln(0.919) \approx -0.084
$$

#### **LLRs for All Bits:**

- $\text{LLR}(b_0) = -0.084$
- $\text{LLR}(b_1) = -0.084$
- $\text{LLR}(b_2) = -0.084$
- $\text{LLR}(b_3) = -0.084$

---

### Comparison to Classical LLR Demapping

#### Classical LLR Demapper
- Involves summing over all constellation points in $S_0$ and $S_1$ for each bit.
- Uses:
  
$$
\text{LLR}(b_k) = \ln\left(\frac{\sum_{x \in S₀} \exp\left(-\frac{|y - x|^2}{2\sigma^2}\right)}{\sum_{x \in S₁} \exp\left(-\frac{|y - x|^2}{2\sigma^2}\right)}\right)
$$

#### **Invention’s Approach:**
- Simplifies the process by avoiding summation over all points.
- Uses closed-form linear expressions to estimate probabilities directly.

#### **Complexity Comparison:**
| **Aspect**               | **Classical LLR Demapper**    | **Invention’s Approach**        |
|--------------------------|-------------------------------|-----------------------------------|
| Distance Calculations    | O(M) per bit             | O(1) per bit                 |
| Exponentials             | O(M)                     | None                             |
| Summation                | O(M/2)                   | None                             |
| Overall Complexity       | O(M ⋅ log(M))       | O(log(M))                   |

---

### Practical Implications
- **Invention's Advantage:**
  - Lower computational complexity makes it ideal for low-power, real-time hardware systems.
  - Simplified computation sacrifices some accuracy but is sufficient for many practical applications.
- **Classical LLR Advantage:**
  - More accurate in high-noise environments due to explicit consideration of all constellation points.


## 4:37-51


This text discusses the calculation of the **first conditional probability vector** $(k=1)$ in a system using a **square QAM constellation**.

1. **Purpose of the Conditional Probability Vector:**
    
    - This vector represents the likelihood of the first bit $(b_1​)$ in a QAM constellation based on the imaginary component $(\beta)$ of the received signal.
    - 
1. **Mathematical Expression 3:**
    
    - The formula for the first conditional probability vector is given as
$$
\frac{1}{2^n} \beta
$$
    - Here:
        - $n$: Determined by the **magnitude of the QAM** constellation.
        - $\beta$: The **imaginary part** of the received signal.
1. Role of $n$
    
    - The value of $n$ depends on the size of the QAM constellation:
        - For $2^n$-QAM, $n$ is the base-2 logarithm of the number of constellation points.
        - Example:
            - 16-QAM: $n=4$ (since $2^4=16$).
            - 64-QAM: $n=6$ (since $2^6=64$).
4. **Output Value Interpretation:**
    
    - The formula $\frac{1}{2^n} \beta$ scales the imaginary part of the received signal to determine the likelihood of the first bit combination.
    - This scaling ensures that the output is normalized based on the constellation size.

- Conditional Probability Representation:
    
    - The value $\frac{1}{2^n} \beta$ provides a soft estimate of the likelihood of the first bit in the bit sequence represented by the QAM symbol.
    - Larger values of $\beta$ indicate a stronger likelihood for certain bit combinations, depending on the constellation layout.

- Simplification in Calculation:
    
    - Instead of calculating complex probability distributions or likelihoods involving all constellation points, the method reduces the computation to a simple linear scaling of the received signal's imaginary component.
Relation to Constellation Size:**
    
    - As the constellation size increases (e.g., from 1616-QAM to 6464-QAM), the scaling factor 12n2n1​ becomes smaller, reducing the impact of ββ on the probability output.

---

### **Example**

#### For 16-QAM ($n=4$):

- Received $\beta=3.2$:
	- Output value = $\frac{1}{2^4} \cdot 3.2 = \frac{1}{16} \cdot 3.2 = 0.2$

#### For 64-QAM ($n=6$):

- Received $\beta=3.2$:
	- Output value=$\frac{1}{2^6} \cdot 3.2 = \frac{1}{64} \cdot 3.2 = 0.05$

This method leverages the structure of the QAM constellation and focuses on reducing computational complexity. By scaling $\beta$ with a power-of-two factor, the approach provides a quick and efficient estimate of the first bit's likelihood without requiring more complex mathematical operations like exponentiation or logarithms.

The description aligns with **Fig. 2** and **Fig. 4**, where the **first bit ($b_1​$)** is determined by the **imaginary component ($\beta$)** of the QAM constellation. Specifically:

**Fig. 2 and Fig. 4 Layout**:
    
- The **upper half of the constellation** corresponds to cases where the first bit ($b_1$​) is **1**.
- This is because $\beta \gt 0$ (positive imaginary values) generally maps to the first bit being **1**.
- Similarly, the **uppermost part of the lower half** (e.g., symbols where $\beta$ is close to 0 but still contributes to $\beta \gt 0$) also ensures that the first bit ($b_1$​) is **1**.

**Explanation via Conditional Probability**:
    
- The formula $\frac{1}{2^n} \beta$ calculates the soft decision likelihood for $b_1​=1$.
    - Positive values of $\beta$ (upper part of the constellation) directly contribute to the first bit ($b_1$​) being more likely 1.
    - The magnitude of $\beta$ impacts the confidence level (e.g., a larger $\beta$ indicates stronger evidence for $b_1​=1$).

**Interpretation of the Constellation**:
    
- **For 16-QAM** (Fig. 2):
        - The symbols in the upper half ($\beta \gt 0$) correspond to $b_1​=1$.
        - The symbols in the lower half ($\beta \lt 0$) correspond to $b_1​=0$.
- **For Larger QAM**:
        - The same principle applies, but the conditional probability vector refines the soft likelihood to account for the finer granularity of larger constellations (e.g., 64-QAM, 256-QAM).


- The description in **4:37–51** and **Mathematical Expression 3** specifically relates to this behavior:
    - The value $\frac{1}{2^n} \beta$ provides a normalized likelihood for $b_1​=1$ based on the imaginary component.
    - As $\beta$ increases, the output value $\frac{1}{2^n} \beta$ becomes larger, confirming $ with greater confidence.
    - Conversely, if $\beta$$ is negative (lower part of the constellation), this output would imply $b_1​=0$.

**First Bit ($b_1$​) Determined by $\beta$:**
    
- Positive $\beta: b_1 = 1$.
- Negative $\beta: b_1 = 0$.

- **Uppermost Symbols in Lower Half:**
    - If the constellation has regions where $\beta \approx 0$ (close to the x-axis), those regions might still contribute to $b_1=1$ depending on the exact threshold and noise conditions.
- **Connection to Probability:**
    - The formula $\frac{1}{2^n} \beta$ elegantly scales $\beta$ to produce the likelihood for $b_1=1$ across varying QAM constellations.

## 4:52-65

For the **second bit ($k=2$)**, the process and its relationship to the QAM constellation can be similarly analyzed, particularly in connection with **Mathematical Expression 4** and its relation to Fig. 2 and Fig. 4.

1. **Text Reference:**
    
    - For $k=2$, the conditional probability vector is calculated using a **different expression** (Mathematical Expression 4). This expression is:
$$
c - \frac{c}{2^{n-1}} \left | \beta \right |
$$

\- Here:
    - $c$: A constant.
    - $n$: The base-2 logarithm of the constellation size ($n=4$ for 16-QAM, $n=6$ for 64-QAM).
    - $\left | B \right |$: The absolute value of the **imaginary component** of the received signal.

**Role of $k=2$:**
    
- The second bit ($b_2$​) for a QAM constellation is determined by the **absolute magnitude of $\beta$** (the imaginary component).
- The formula $c - \frac{c}{2^{n-1}} \left | \beta \right |$ represents the **soft likelihood** of $b_2=1$.

### Behavior of the Formula

- **Scaling Effect:**
    
    - $c - \frac{c}{2^{n-1}} \left | \beta \right |$ decreases as $\beta$ increases.
        - For example:
            - If $\left | \beta \right | \rightarrow 0$ : The output approaches $c$, indicating a high likelihood for one specific bit value ($b_2=1$ or $b_2=0$).
            - If $\left | \beta \right | \rightarrow  \text{max}(\beta)$: The output approaches $c−c=0$, indicating a low likelihood.
- **Absolute Magnitude and b2b2​:**
    - For QAM constellations, $\left | \beta \right |$ divides the imaginary axis into regions:
        - Lower magnitudes ($\left | \beta \right | \lt \text{threshold}$) favors $b_2=1$.
        - Higher magnitudes ($\left | \beta \right | \gt \text{threshold}$) favors $b_2=0$.
- **Impact of $n$:**
    - The factor $2^{n−1}$ adjusts the sensitivity of the formula for larger constellations.
    - Larger nn (e.g., 6464-QAM vs. 1616-QAM) makes the formula less sensitive to small changes in $\left | \beta \right |$, as the step size decreases.

---

### **Application to Fig. 2 and Fig. 4**

- **Relationship to the Imaginary Component ($\beta$):**
    
    - For the second bit ($b_2$​), the absolute magnitude $\left | \beta \right |$ determines the likelihood.
    - In **Fig. 4**, $\left | \beta \right |$ separates the **upper and lower halves** of each quadrant:
        - Smaller $\left | \beta \right |: b_2=1$.
        - Larger $\left | \beta \right |: b_2=0$.
- **Key Regions in the Constellation:**
    
    - **Upper Quadrants ($\beta \gt 0$):**
        - **Top center** of the quadrants (small $\left | \beta \right |$) will likely favor $b_2=1$.
        - **Farther edges** (large $\left | \beta \right |$) will likely favor $b2=0$.
    - **Lower Quadrants ($\beta \lt 0$):**
        - Similar behavior applies, but now mirrored across the x-axis.

---

### **Example Calculation**

#### Given:

- **Received $\beta=1.8$** (imaginary part).
- $n=4$ (for 16-QAM).
- **Constant $c=1$**.

- Compute:
$$
\text{Output value} = c - \frac{c}{2^{n-1}}\left | \beta \right |
$$
    Substituting values:
    $$
    \begin{gather}
    \text{Output value} = 1 - \frac{1}{2^{4-1}} \cdot \left | 1.8 \right | = 1 - \frac{1}{8} \cdot 1.8 \\
    \text{Output value} = 1 - 0.225 = 0.775
    \end{gather}
    $$
- Interpretation:
    
    - The output 0.775 represents the likelihood of $b_2=1$.
    - A higher likelihood indicates that $b_2=1$ is more probable given the received $\left | \beta \right | = 1.8$.

- **Behavior Across Fig. 4:**
    
    - For regions closer to the x-axis ($\left | \beta \right | \rightarrow 0$), the formula outputs higher values, favoring $b_2=1$.
    - For regions farther from the x-axis ($\left | \beta \right |$ larger), the likelihood decreases, favoring $b_2=0$.
- **Comparison to $k=1$:**
    
    - For $k=1, \beta (not $\left | \beta \right |$) directly determines the bit likelihood.
    - For $k=2$, $\left | \beta \right |$ (absolute magnitude) governs the probability, making it less sensitive to the sign of $\beta$.