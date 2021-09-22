# QOSF_Screening
Solution to the screening task, for QOSF Mentorship Program

Cohort 4
Task No.1 by Rodrigo Rosado Rivial

This screening task for the QOSF metorship program consists in creating a quantum circuit that will take as input a vector of values and outputs a superposition state of the indices of those values of the vector that have a binary representation that has no equal bits directly adjacent (i.e. any number with '...00...' or '...11...' in its binary representation is discarded). 

The general solution was sought for, so any vector of 'n' positive integer values with binary representation of 'm' bits lenght can be inputed. To solve this, the following steps were taken.

  1. Input vector is translated into binary values. Data like the lenght of the largest number in the vector, the lenght of the vector and the lenght of the largest binary representation is saved to be used later in the solution.
  2. Using itertools, all possible bitstrings of lenght 'm' are obtained. The bitstrings with '...00...' or '...11...' are discarded, and the "good states" are saved into a list and cleared of any leading zeros.
  3. Grovers algorithm is executed to check the inputed list for any of the good states. The indices of any match are saved and printed along with its respective states.
