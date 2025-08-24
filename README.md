Title: Comparative Analysis of Algorithms for the Travelling Salesman Problem (TSP)
Team members- 
Srija Nallamothu (M16155365)
Rama Krishnam Raju Alluri (M16194241)
Yutika Agarwal ( M16501686)
Jahnavi Kulkarni (M16453493)

Abstract
This study explores the comparative performance of four nature-inspired optimization algorithms — Ant Colony Optimization (ACO), Glowworm Swarm Optimization (GSO), Genetic Algorithm (GA), and Particle Swarm Optimization (PSO) — in solving the Traveling Salesman Problem (TSP). Through empirical evaluation across three datasets (att48, berlin52, and bier127), we investigate each algorithm’s capability in terms of solution quality, execution time, and memory consumption. Our hypothesis posits that swarm-based strategies (GSO, ACO) are better suited for larger and more complex TSP instances. Results confirm the hypothesis, albeit revealing significant trade-offs in computational cost.
1. Introduction
The Travelling Salesman Problem (TSP) remains a canonical NP-hard problem, stimulating the development of numerous heuristic and metaheuristic approaches. This report investigates the potential of nature-inspired metaheuristics, particularly those mimicking collective behavior in nature, to efficiently approximate solutions for TSP.
We focus on:
Ant Colony Optimization (ACO): Inspired by pheromone-laying behavior of ants.
Glowworm Swarm Optimization (GSO): Models firefly-like luminescence-driven movement.
Genetic Algorithm (GA): Evolves candidate solutions via mutation and crossover.
Particle Swarm Optimization (PSO): Mimics social interaction among moving particles.


2. Method
Datasets:
att48.tsp (48 cities)
berlin52.tsp (52 cities)
bier127.tsp (127 cities)


Each algorithm was executed two times per dataset. We collected:
Best Distance (quality of solution)
Execution Time (ms)
Peak Memory Usage (MB)

Hyperparameters:
For the Glowworm Swarm Optimization (GSO) algorithm, the number of glowworms was set to 50, and the maximum number of iterations was 200. A key parameter, GAMMA, which influences the decision range for neighbor selection, was set to 0.6. Additionally, luciferin decay and enhancement rates were 0.4 and 0.6 respectively, and the neighborhood range was fixed at 5. To enhance performance, we applied both city swap and 2-opt local search strategies. Glowworm brightness was defined as the inverse of the total tour distance, encouraging shorter paths.
In Ant Colony Optimization (ACO), the number of ants was equal to the number of cities in the problem. The algorithm used a pheromone importance factor alpha of 1.0 and a heuristic importance beta of 5.0, with a pheromone evaporation rate rho of 0.5 and a deposit constant Q of 100. The number of iterations varied around 100–200 depending on the dataset.
For the Genetic Algorithm (GA), a population size of 100 was used, with a crossover rate of 0.8 and a mutation rate of 0.2. Selection was carried out using either tournament or roulette wheel methods, and elitism was enabled to preserve the best solutions. The algorithm was typically run for 200 generations.
Finally, in Particle Swarm Optimization (PSO), 50 particles were used. The inertia weight was set to 0.7 to balance exploration and exploitation, while both the cognitive and social coefficients were set to 1.5. The number of iterations was 200, and the solution representation was customized using a permutation-based encoding suitable for the TSP.


3. Results and Discussion
City Size 
ACO, PSO are considered to be the best algorithms for TSP problems. We believed GSO had the ability to perform even better than ACO. 
Change made to make GSO better: Incorporating city swap and 2-opt local search in Glowworm Swarm Optimization (GSO) improves its performance on the Traveling Salesman Problem (TSP) by enhancing both exploration and exploitation, leading to shorter tour distances and more efficient solutions.
Rationale:
City Swap: By allowing glowworms to swap cities with their neighbors, the algorithm introduces diversity and exploration into the search space. This helps avoid local optima by facilitating the exploration of different parts of the solution space, which is crucial for a problem like the TSP (Traveling Salesman Problem) where the solution landscape is highly complex. The swap encourages a more dynamic search process, where glowworms are not only improving their individual tours but also interacting with other glowworms, leading to a better global search.

4. Conclusion
This study compared four nature-inspired algorithms—Ant Colony Optimization (ACO), Glowworm Swarm Optimization (GSO), Genetic Algorithm (GA), and Particle Swarm Optimization (PSO)—on solving the Traveling Salesman Problem (TSP) across datasets of increasing complexity. The evaluation focused on solution quality, execution time, and memory usage to identify the strengths and trade-offs of each approach. As shown in Figure 1, GSO, enhanced with 2-opt local search and city swap mechanisms, delivered the best performance in terms of shortest tour distances, especially on the larger dataset (bier127). These improvements enabled better exploration and refinement of routes. ACO also performed consistently well across all datasets, while GA and PSO showed reduced accuracy with increasing problem size, likely due to premature convergence. Figure 2 visually confirms GSO’s improved performance on berlin52, where the tour is compact and well-optimized with a distance of 33,555.28. Figure 3 further demonstrates GSO’s stability, with low variability across multiple runs. ACO remained reliable, while GA and PSO produced more scattered results, indicating inconsistency. However, this accuracy came at a cost. Figure 4 highlights GSO’s high computational time, averaging over 200,000 ms, far higher than the nearly instant runtimes of the other methods. Figure 5 also shows that both GSO and ACO consumed more memory (0.29 MB and 0.52 MB), in contrast to the very lightweight GA and PSO (<0.01 MB).
In summary, GSO offers high accuracy and robustness, especially for large TSP instances, but at the expense of speed and memory. ACO provides a strong balance between performance and efficiency. GA and PSO, while less accurate, are highly efficient and suitable for real-time or resource-limited environments. The choice of algorithm should ultimately depend on whether the priority is solution quality or computational efficiency.




