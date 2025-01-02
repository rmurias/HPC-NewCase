
### Log-Likelihood Ratios (LLRs) in Demodulation and Soft Decision Making

Log-Likelihood Ratios (LLRs) play a critical role in soft decision decoding, particularly in modern communication systems that employ error-correcting codes like Turbo or LDPC codes. Here's a detailed explanation of how LLRs are used in demodulation and soft decisions:

---

### 1. **Definition of LLR**

An **LLR** quantifies the likelihood of a received signal corresponding to a particular transmitted bit. It is defined as the natural logarithm of the ratio of probabilities of two competing hypotheses for a binary decision:

$$
LLR(b_k)=ln ⁡\left( \frac{Pr⁡(b_k=1∣ReceivedSignal)}{Pr⁡(b_k=0∣ReceivedSignal)} \right)
$$

Where:

- $b_k$​ is the $kk^{th}$ transmitted bit.
- $Pr⁡(b_k=1∣ReceivedSignal)$ is the posterior probability of $b_k=1$.
- $Pr⁡(b_k=0 ∣ ReceivedSignal)$ is the posterior probability of $b_k​=0$.

---

### 2. **LLRs in Soft Demodulation**

Soft demodulation uses the received signal and channel model to calculate the LLR for each transmitted bit. Here's how this process works:

#### a. **Received Signal and Noise Model**

- The received signal yy is modeled as:
$$
y = h \cdot x + n
$$
where:

- $x$ is the transmitted symbol.
- $h$ is the channel coefficient (e.g., fading or gain).
- $n$ is additive white Gaussian noise (AWGN) with variance $\sigma^2$.

#### b. **Symbol Mapping**

For modulation schemes like BPSK, QPSK, or higher-order QAM, each transmitted bit bkbk​ is mapped to a symbol xx in the constellation. For example:

- In BPSK: $b_k \in \{0,1\}$, mapped to $x \in \{−1,+1\}$.
- In QPSK: $b_k \in \{00,01,10,11\}$, mapped to symbols like $x \in \{ \pm 1, \pm j\}$.

#### c. **Conditional Probabilities**

For a received signal $y$, the conditional probability of observing $y$ given that $b_k=1$ or $b_k=0$ can be expressed as:

$$
Pr(y \mid b_k)  \propto exp \left (- \frac{\mid y - h \cdot x \mid ^2}{2 \sigma ^2} \right )
$$

Here, $x$ corresponds to the symbol associated with $b_k=1$ or $b_k=0$.

#### d. **LLR Calculation**

The LLR is then computed as:

LLR(bk)=ln⁡(∑x∈X1exp⁡(−∣y−h⋅x∣22σ2)∑x∈X0exp⁡(−∣y−h⋅x∣22σ2))LLR(bk​)=ln​∑x∈X0​​exp(−2σ2∣y−h⋅x∣2​)∑x∈X1​​exp(−2σ2∣y−h⋅x∣2​)​​

Where:

- X1X1​ is the set of symbols corresponding to bk=1bk​=1.
- X0X0​ is the set of symbols corresponding to bk=0bk​=0.

For BPSK, this simplifies because each bit maps to a single symbol, but for higher-order modulation, the summation accounts for all possible symbols that could correspond to bk=1bk​=1 or bk=0bk​=0.

---

### 3. **Making Soft Decisions**

The computed LLR values are passed to the decoder as soft information:

- **Positive LLR**: Indicates higher confidence that bk=1bk​=1.
- **Negative LLR**: Indicates higher confidence that bk=0bk​=0.
- **Magnitude of LLR**: Represents the confidence level of the decision (larger magnitude implies higher confidence).

This soft information is used in iterative decoding algorithms (e.g., in Turbo or LDPC decoders) to improve the error correction capability by leveraging the probabilistic information.

---

### 4. **Example: BPSK over AWGN**

For BPSK, where x∈{−1,+1}x∈{−1,+1} and h=1h=1, the LLR simplifies to:

LLR(bk)=2yσ2LLR(bk​)=σ22y​

- If y>0y>0, the LLR is positive, favoring bk=1bk​=1.
- If y<0y<0, the LLR is negative, favoring bk=0bk​=0.

---

### 5. **Advantages of LLRs**

- **Improved Decoding**: Soft decisions using LLRs provide more information to the decoder than hard decisions, enhancing error correction performance.
- **Iterative Decoding**: LLRs allow decoders to refine decisions iteratively based on probabilistic information.

---

### 6. **Applications**

- Turbo and LDPC coding schemes in 4G/5G systems.
- Satellite communication and deep-space missions.
- Wi-Fi and other wireless communication standards.

---

By leveraging LLRs, communication systems achieve robust performance, especially in noisy or fading channels.