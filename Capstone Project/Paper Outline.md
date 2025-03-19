## Application of Local Time-Stepping for Adaptive Mesh Refinement in Simulated Binary Neutron Star Mergers



 - Scientific Motivation
	 - Why are BNSMs important for astrophysics?
	 - Equation of state and connection to Neutron Stars.
	 - Recent advancements in astrophysics (theoretical & exp).
	 - The importance of BNSM simulations and their role in astrophysics.









 - Scientific Motivation
	 - Why are BNSMs important for astrophysics?
	 - The importance of BNSM simulations and their role in astrophysics.
 - Equation of State












 - Computational Challenges
	 - Why these simulations are resource-intensive and the need for optimization.
 - Project Focus (scope)
	 - Instead of simulating full GR, this work focuses on Adaptive Mesh Refinement (AMR) + Dynamic Time Scaling (DTS).
	 - A simplified alternative physical system will be used in Python to test these techniques.
 - Paper Organization
	 - Overview of sections.



2. Theoretical and Computational Background (Subsections)
Binary Neutron Star Mergers (BNSMs)
Their astrophysical significance and connection to gravitational waves.
Computational Complexity in BNSM Simulations
Why these simulations are difficult (multi-scale nature, computational cost, need for AMR).
Alternative Systems for Testing AMR + DTS
Since full GR is infeasible, an adjacent physical system will be used in Python.
Potential alternatives:
Newtonian fluid simulations with density variations.
Plasma physics models with evolving energy densities.
Simplified wave equations with varying stiffness.



3. Computational Framework (Subsections)
Software & Toolkits
Einstein Toolkit: Why it was initially considered.
Issues with SPORC and why a different approach was needed.
Hardware & High-Performance Computing (HPC) Setup
Computational resources used (local machine, clusters, parallelization strategies).
Python Implementation
What system is being simulated instead of full GR (to be clearly defined).
How AMR + DTS are incorporated into the Python model.



4. Adaptive Mesh Refinement (AMR) + Dynamic Time Scaling (DTS)   (Subsections)
Adaptive Mesh Refinement (AMR)
Why AMR improves computational efficiency.
How AMR is implemented in your Python simulation.
Dynamic Time Scaling (DTS)
Core Idea: Increase delta-time in regions where the Stress-Energy tensor (or analogous quantity) is small.
Theoretical justification: How this balances efficiency and accuracy.
Implementation details: How DTS integrates into the simulation.
Expected Benefits and Potential Drawbacks
Where AMR + DTS should improve performance.
Possible accuracy trade-offs.



5. Benchmark Profiling Analysis (Analyzing bottlenecks in Einstein Toolkit and Python)
Profiling Data from Einstein Toolkit
Analysis of where the most time was spent in Einstein Toolkit.
How AMR + DTS might address these bottlenecks.
Profiling Your Python Implementation
Identifying which parts of the Python simulation take the most time.
Baseline runtime comparison before and after AMR + DTS.



6. Capstone I: Einstein Toolkit Setup and Baseline Performance Analysis
Setting Up Einstein Toolkit
Installation process and challenges (including SPORC compilation issues).
Configuration of ETK for BNSM simulations.
Attempting Baseline Performance Profiling
Initial profiling attempts to identify computational bottlenecks.
What worked and what didn’t in terms of extracting performance data.
Limitations encountered that led to considering an alternative approach.
Capstone I Tables/Graphs (Einstein Toolkit Baseline Analysis)
Table of benchmarking results from ETK (where time was spent).
Graph: Execution time per ETK module (profiling results).
Graph: Scaling behavior of ETK with resolution (if applicable).




7. Capstone II: Python Simulation with AMR + Dynamic Time Scaling
Motivation for an Alternative Approach
Why moving to a Python-based simulation made sense after issues with ETK.
Decision to focus on AMR + Dynamic Time Scaling instead of full GR.
Developing the Python Simulation
Description of the simplified physical system used in Python.
Implementation of AMR in this model.
Implementing Dynamic Time Scaling
How time-stepping was adjusted based on the Stress-Energy tensor (or equivalent).
Expected performance improvements.
Performance Comparison and Profiling
Measuring efficiency gains from AMR + DTS vs. fixed time-stepping.
Identifying remaining performance limitations.
Capstone II Tables/Graphs (Python Simulation & AMR + DTS Results)
Table of Python runtime performance with & without AMR/DTS.
Graph: Speedup factor for different time step adjustments.
Graph: Error vs. Time Step Size (to show accuracy trade-offs).
Graph: Refined Grid Size Over Time (to visualize AMR efficiency).



8. Discussion (Narrative)
Impact of AMR + DTS: How these methods can be useful in real astrophysical simulations.
Limitations: Where AMR + DTS might fail or require further refinement.
Future Work:
Extending AMR + DTS to more complex physical systems.
Exploring GPU acceleration for further performance gains.



9. Conclusion (Narrative)
Summary of Key Findings:
AMR + DTS can improve efficiency in computational simulations.
Trade-offs between speed and accuracy.
Future Research Directions: How this concept could be extended to full BNSM simulations.



10. Acknowledgments & References


Waves (Wave Equation) in Inhomogeneous Medium
Why: Common example and familiar.
Pros: Simple, has a hyperbolic PDE, AMR works in it already.
Cons: 

Newtonian Fluid Flow with Density Variations
Why: Classic example for simulations in CS and Physics.
Pros: Closer to GR(M)HD, where the optimization is much needed.
Cons: Much more computationally expensive.



