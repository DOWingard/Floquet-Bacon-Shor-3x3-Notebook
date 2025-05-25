# Floquet-Bacon-Shor code on a 3x3 lattice

## THIS IS A WORK IN PROGRESS

## This is a prototype notebook for a Floquet-Bacon-Shor code, built following Ref(1), which applies the work of Ref(2) AND Ref(3)

The details related to periodic subsystems codes and the Instaneous Stabilizer Groups (ISG) are found in the following papers:

1. https://arxiv.org/pdf/2503.03867
2. https://arxiv.org/pdf/2403.03291
3. https://arxiv.org/pdf/2107.02194

There are also slides from a presentation given on Floquet-Bacon-Shor code:

https://ntrs.nasa.gov/api/citations/20240004137/downloads/Floquet_Bacon_Shor_MQC_Apr2024.pdf

## The code works as follows 

* The cycles are split into period 4 measurement schedule, where four weight-2 gauge checks are measured. The mod2 sum of the gauge checks suffice for a weight-6 stabilizer with a gauge defect
* After one measurement cycle, the codespace reaches a steady state as the full instaneous stabilizer group has been constructed
* Successive measurement cycles build a syndrome history, where the ancilla measurements are compared with the results from the prior measurement period to build a detector (hyper-)graph
* The two logical qubits Z_s, and Z_d are measured and a minimum weight perfect matching solution is found for the detector (hyper-)graph
* The logical measurements are decoded and the results are displayed, as well as the detector (hyper-)graph


## Important notes:

* The 3x3 system is insufficient to provide error correction to the dynamic qubit, but in practice, both complete weight-6 Z stabilizers would be measured prior to the logical measurements Z_s,Z_d to provide fault tolerance. 
* The dynamic logical qubit picks up a parity dependent on previous gauge measurements and that is not implimented in this code at this point
