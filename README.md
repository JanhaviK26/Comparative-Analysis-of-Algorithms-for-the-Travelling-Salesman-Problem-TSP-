Title: Comparative Analysis of Algorithms for the Travelling Salesman Problem (TSP)

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




