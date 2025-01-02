
### **Claim 1**

**Explanation**: This claim describes the core soft decision demodulation method for QAM signals. It involves:

- Receiving the QAM signal with in-phase (**α**) and quadrature phase (**β**) components.
- Using conditional probability vectors (soft decision values) to determine the bit positions.
- A process to demodulate the first and second halves of the bit sequence by swapping the in-phase and quadrature components.
- Using the same computational method for odd and even bits, with adjustments based on the signal’s constellation diagram.

This establishes a framework for improved accuracy and processing efficiency in demodulation.

---

### **Claim 2**

**Explanation**: This claim specifies how to calculate the **first conditional probability vector**:

- One of the components (**α** or **β**) is selected based on the constellation diagram form.
- A mathematical function is applied to the selected component to compute the output.

This allows for flexible adaptation of the demodulation method to different QAM constellations.

---

### **Claim 3**

**Explanation**: This claim focuses on determining the **second conditional probability vector**:

- The previously unselected component (**β** if **α** was used, or vice versa) is substituted into the computation.
- This method ensures balanced processing of the two components.

It enables consistent and accurate calculation of soft decisions across signal components.

---

### **Claim 4**

**Explanation**: This claim extends the computation to the **third conditional probability vector**:

- Similar to the first vector, it involves selecting one of the components (**α** or **β**) and applying specific mathematical equations.
- The formula accounts for the magnitude of the QAM and constants specific to the signal.

This supports higher-order computations needed for more complex QAM constellations.

---

### **Claim 5**

**Explanation**: This claim calculates the **fourth conditional probability vector**:

- It builds on the third vector by substituting each selected signal component with its counterpart (e.g., swapping **α**with **β** or vice versa).
- The process accounts for cases where **α > 0** or **β < 0**, ensuring complete coverage of the constellation diagram.

It ensures accuracy for symmetric and asymmetric constellation points.

---

### **Claim 6**

**Explanation**: This claim determines the **fifth conditional probability vector**:

- Similar to previous claims, it selects a signal component and substitutes the values according to the constellation diagram's structure.
- Mathematical formulas provide the output for the vector.

This handles the increasing complexity of high-order QAM.

---

### **Claim 7**

**Explanation**: This claim calculates the **sixth conditional probability vector**:

- Specifically for 64-QAM, it uses substitution methods to compute the vector, extending the process from earlier claims.

This enables efficient handling of mid-order QAM constellations.

---

### **Claim 8**

**Explanation**: For high-order QAM (greater than 256-QAM):

- Conditional probability vectors are computed for a large number of bits (e.g., 5th to 2n2n).
- Mathematical expressions and substitutions are tailored for these complex constellations.

This optimizes the demodulation process for scenarios with dense constellation points.

---

### **Claim 9**

**Explanation**: Extends Claim 8 to cover conditional probability vectors for n+3n+3 to 2n2n bits:

- These vectors are calculated by substituting selected components (**α** and **β**) and applying transformations.

This ensures efficient and scalable computation for large numbers of bits.

---

### **Claim 10**

**Explanation**: Revisits the first conditional probability vector with additional specificity:

- Describes selecting either **α** or **β** and applying predefined mathematical expressions.
- This reinforces the adaptability of the method to different constellation diagram forms.

---

### **Claims 11–29**

**Explanation**: These claims elaborate further on:

- Conditional probability vector computations for **specific QAM orders**.
- Adjustments for lower-order QAM (<64-QAM) and specialized methods for higher-order QAM (≥256-QAM).
- Iterative substitutions of signal components and transformations specific to the QAM constellation diagram.

These claims ensure comprehensive coverage of QAM orders, allowing the method to handle a wide range of modulation scenarios.

---

### **Summary**

This patent provides a systematic approach to QAM demodulation using conditional probability vectors. Each claim adds specific steps or refinements to the computation process, ensuring compatibility with different QAM orders and constellation diagram forms. The emphasis on iterative substitution and shared computational methods across bits enhances processing speed and reduces hardware complexity.
