# QOSF_Screening
Solution to the screening task, for QOSF Mentorship Program

Cohort 4
Task No.1 by Rodrigo Rosado Rivial

This screening task for the QOSF metorship program consists in creating a quantum circuit that will take as input a vector of values and outputs a superposition state of the indices of those values of the vector that have a binary representation that has no equal bits directly adjacent (i.e. any number with '...00...' or '...11...' in its binary representation is discarded). 

The general solution was sought for, so any vector of positive integer values with binary representation of 'm' bits lenght can be inputed. To solve this, the following steps were taken.

  1. Input vector is translated into binary values. Data like the lenght of the largest number in the vector 'm', the lenght of the vector 'l', and the minimum number of bits needed to encode any index of the list 'n' is saved to be used later in the solution.
  2. Using itertools, all possible bitstrings of lenght 'm' are obtained. The bitstrings with '...00...' or '...11...' are discarded, and the "good states" are saved into a list and cleared of any leading zeros.
  3. Grovers algorithm is executed to check the inputed list for any of the good states. The indices of any match are saved into a variable and printed along with its respective states.
  4. The saved indices are then transformed into vectors to represent the respective quantum state (i.e. Whenever a 0 is found in an index it is made into the vector (1,0) and when a 1 is found, it is made into the vector (0,1). As an example: Index (11) is made into ((0,1)(0,1)).
  5. Then a tensor product of all vectors in an index is calculated and saved as a statevector. This is done for both indexes (when there are two indexes), and the result is then saved as a final statevector. The vector is then normalized.
  6. The normalized vector is then introduced into a QuantumCircuit with 'n' qubits, using the initialize method.
  7. Finally the circuit is executed using the "statevector_simualtor" backend and results are shown in a histogram. The states that result from the statevector simulation represent the indexes.
