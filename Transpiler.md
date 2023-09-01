Transform an abstract [[Quantum Circuit]] to a physical one. 
It represent the circuit as a [[DAG - Directed Acyclic Graph]], and apply some transformation called *Pass* to it. The *PassManager* combine Passes and control flow. This model is used to develop techniques to [[Error Suppression and mitigation|mitigate errors]] in noisy quantum hardware.

## Translation

Transform the transpiled circuit into gates known by the actual quantum hardware used.

## Scheduling

Create a schedule for the actual [[pulses]] to be sent to the hardware.