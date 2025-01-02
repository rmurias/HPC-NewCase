
The combinational constellation diagram of QAM may be generally divided into 3 types or forms according to the arrangement of bit bundles assigned to the constellation points. The first form is a form with a constellation as shown in FIGS. 2 to 4, the second is a form with a constellation as shown in FIGS. 5 to 7, and the third is a form that is not included in this application.

## First Form

Note the first form (Fig. 2) is the IEEE 802.11 constellation for 16-QAM.

![[7580480 Fig. 2.png]]

![[7580480 Fig. 3.png]]

![[7580480 Fig. 4.png]]

## Second Form

Note this form of the 16-QAM constellation corresponds to the 3GPP implementation.

![[7580480 Fig. 5.png]]

![[7580480 Fig. 6.png]]
![[7580480 Fig. 7.png]]



The demodulation method of a square QAM signal is divided into 2 forms (see the "Disclosure of the Invention" section, above), and first and third embodiments are used for the first form and second and fourth embodiments are used for the second form.

## First Embodiment

The first embodiment of the present invention is a case corresponding to the first form. The first embodiment includes an example of 1024-QAM where the magnitude of QAM is 1024. The order selection of the received signal is intended to apply $\alpha$ in the first half and $\beta$ in the second half.


- Focuses on the first form of QAM with a square constellation.
- Demodulation uses one signal component (real or imaginary) for the first half of the bits and the other for the second half.
- A conditional probability vector for each bit is calculated using mathematical expressions tailored for simplicity and efficiency.

## Second Embodiment

The second embodiment of the present invention is a case corresponding to the second form. The second embodiment includes an example of 1024-QAM where the magnitude of QAM is 1024. The order selection of the received signal is intended to apply $\alpha$ first.

- Corresponds to the second form of QAM.
- Utilizes alternating components (real and imaginary) for calculating the conditional probability vectors of odd- and even-ordered bits.
- The method ensures consistency and efficiency in handling larger QAM constellations.

## Third Embodiment

The third embodiment of the present invention is a case corresponding to the first form and is applied the property of the first form. The third embodiment includes an example of 1024-QAM where the magnitude of QAM is 1024. The order selection of the received signal is intended to apply $\alpha$ in the first half and $\beta$ in the second half. (referring to FIGS. 11 and 12).

![[7580480 Fig. 11.png]]

![[7580480 Fig. 12.png]]
    
- Applies the first form of QAM with a focus on enhancing computation for larger magnitudes, such as 1024-QAM.
- Similar to the first embodiment but optimized with iterative calculation approaches for better hardware implementation.

## Fourth Embodiment

The fourth embodiment of the present invention is a case corresponding to the second form and is applied the property of the second form. The fourth embodiment includes an example of 1024-QAM where the magnitude of QAM is 1024. The order selection of the received signal is intended to apply $\alpha$ at first.

- Relates to the second form of QAM but incorporates optimizations for large QAM magnitudes (e.g., 1024-QAM).
- Further divides and refines the conditional probability vector computation to handle asymmetrical output ranges and complex constellations.
