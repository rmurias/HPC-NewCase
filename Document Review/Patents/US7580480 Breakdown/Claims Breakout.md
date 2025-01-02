
# Claims of Patent US7580480

---

## Claim 1
A soft decision method for demodulating a received signal **α+βi** of a square Quadrature Amplitude Modulation (QAM) consisting of an in-phase signal component and a quadrature phase signal component, comprising:
1. Receiving the signal **α+βi** in a radio communication apparatus;
2. Obtaining a plurality of conditional probability vector values, each being a soft decision value corresponding to a bit position of a hard decision, using a function including a conditional determination operation from the quadrature phase component and the in-phase component of the received signal;
3. **Wherein** a conditional probability vector decision method for demodulating a first half of a total number of bits is the same as a decision method for demodulating the remaining half of the bits, and is determined by substituting a quadrature phase component value and an in-phase component value with each other; and
4. **Wherein** the demodulation method of the conditional probability vector corresponding to an odd-ordered bit is the same as the calculation method of the conditional probability vector corresponding to the next even-ordered bit, where the received signal value used to calculate the conditional probability vector corresponding to the odd-ordered bit uses one of the **α** and **β** values according to a given combination constellation diagram, and the received signal value for the even-ordered bit uses the remaining one of **α** and **β**.

---

## Claim 2
The method according to claim 1, wherein a first conditional probability vector is determined by selecting any one of the received signal components **α** and **β** according to a form of a combination constellation diagram, and then according to the following mathematical expression:
- The output value is unconditionally determined as:

\[ \text{output} = a \cdot f(\text{selected component}) \]

---

## Claim 3
The method according to claim 2, wherein a second conditional probability vector is determined by substituting the received value selected with the received value that is not selected in the method for obtaining the first conditional probability vector.

---

## Claim 4
The method according to claim 1, wherein a third conditional probability vector is determined by selecting one of the received values **α** and **β** according to a form of a combination constellation diagram, using the following mathematical expression (B):

\[ \text{output} = g(\text{selected value, magnitude of QAM, constants}) \]

---

## Claim 5
The method according to claim 4, wherein a fourth conditional probability vector is calculated by substituting each of the received values used with each of the received values that are not used in the method for obtaining the third conditional probability vector in the cases of **α > 0** and **β < 0**.

---

## Claim 6
The method according to claim 1, wherein a fifth conditional probability vector is determined by selecting one of the received values **α** and **β** according to the form of the combination constellation diagram, and substituting the received value selected with the remaining value in specific mathematical expressions.

---

## Claim 7
The method according to claim 6, wherein when the magnitude of QAM is 64-QAM, a sixth conditional probability vector is calculated by substituting each of the received values used with each of the received values that are not used in the method for obtaining the fifth conditional probability vector.

---

## Claim 8
The method according to claim 1, wherein when the magnitude of QAM is greater than 256-QAM, fifth to \(2^n\) conditional probability vectors are determined by selecting one of the received values **α** and **β**, and substituting them according to mathematical expressions specific to high-order QAM constellations.

---

## Claim 9
The method according to claim 8, wherein when the magnitude of QAM is more than 256-QAM, additional conditional probability vectors (\(n+3\) to \(2n\)) are selected by substituting specific received values and using mathematical transformations.

---

## Claim 10
The method according to claim 1, wherein the first conditional probability vector is determined by selecting either **α** or **β**, and applying specific mathematical expressions to compute the soft decision output.

---

## Claim 11-29
These claims further elaborate on methods for computing conditional probability vectors for different orders of QAM, including:
- Specific formulas for low-order QAM (\(< 64\)-QAM).
- Specialized handling for higher-order QAM (\(\geq 256\)-QAM).
- Adjustments based on constellation diagrams and iterative substitution of selected signal components (**α** and **β**) in mathematical expressions.

---

This markdown document summarizes the key claims. Let me know if you'd like further details or examples from the mathematical expressions in specific claims.
