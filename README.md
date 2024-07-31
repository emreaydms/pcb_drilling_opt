# PCB Drilling Optimization Using TSP

## Overview

This project presents an alternative solution for optimizing the drilling path on printed circuit boards (PCBs) by applying three different optimization algorithms to the Traveling Salesman Problem (TSP). The algorithms used are Genetic Algorithm (GA), Simulated Annealing (SA), and Particle Swarm Optimization (PSO).

## Table of Contents

- [Introduction](#introduction)
- [Problem Definition](#problem-definition)
- [Background](#background)
- [Assumptions](#assumptions)
- [Methods](#methods)
  - [Genetic Algorithm (GA)](#genetic-algorithm-ga)
  - [Simulated Annealing (SA)](#simulated-annealing-sa)
  - [Particle Swarm Optimization (PSO)](#particle-swarm-optimization-pso)
- [Implementation](#implementation)
- [Working Mechanism](#working-mechanism)
- [Performance Evaluation](#performance-evaluation)
- [Visualization](#visualization)
- [Results and Discussion](#results-and-discussion)
- [References](#references)

## Introduction

The Traveling Salesman Problem (TSP) is a well-known NP-hard problem that involves finding the shortest possible route for a salesman to visit a list of cities and return to the starting point. This project applies TSP to optimize the drilling path on PCBs, reducing travel time and improving manufacturing efficiency.

## Problem Definition

To connect conductors on different layers or position the pins of integrated circuits, holes of various diameters must be drilled through the PCB. The drilling head must minimize travel time by drilling all holes of the same diameter consecutively before changing tools. This problem is modeled as a series of TSPs, one for each drill size, with the objective of minimizing the travel time for the drilling head.

## Background

PCBs are essential components in modern electronics, connecting various parts and ensuring proper functionality. Efficient drilling paths reduce manufacturing time, minimize material wastage, and conserve resources, which is crucial for productivity and environmental sustainability.

## Assumptions

Each drilling point is considered a node, and the path followed by the drilling machine is the minimized path. Coordinates of each hole are determined by applying imaginary grid lines on the PCB surface.

## Methods

### Genetic Algorithm (GA)

GA is a population-based optimization technique inspired by natural selection. It evolves a population of solutions using genetic operators such as crossover, mutation, and selection. The algorithm iterates until an optimal or near-optimal solution is found.

### Simulated Annealing (SA)

SA is a probabilistic optimization technique that explores the solution space by accepting probabilistic improvements and occasional worse solutions. It gradually decreases the temperature parameter to balance exploration and exploitation, converging towards an optimal solution.

### Particle Swarm Optimization (PSO)

PSO is inspired by the social behavior of birds and fish. It adjusts the positions of particles based on personal and global best solutions, iteratively refining the search process to converge towards an optimal solution.

## Implementation

The implementation involves reading PCB hole coordinates from a CSV file, dividing the dataset into parts based on drill sizes, and applying the three optimization algorithms to each part separately.

## Working Mechanism

### Genetic Algorithm (GA)

- **Initialization:** Generate a random population of candidate solutions.
- **Crossover and Mutation:** Combine segments of parent solutions and introduce mutations to maintain diversity.
- **Selection:** Use tournament selection to choose individuals for reproduction based on fitness.
- **Termination:** Run for a predefined number of generations or until convergence.

### Simulated Annealing (SA)

- **Initialization:** Generate an initial solution randomly.
- **Annealing Schedule:** Start with a high temperature and gradually decrease it.
- **Acceptance Criteria:** Accept new solutions based on fitness and temperature.
- **Termination:** Continue until the temperature drops below a threshold.

### Particle Swarm Optimization (PSO)

- **Initialization:** Initialize a swarm of particles with random positions.
- **Velocity and Position Update:** Adjust velocities and positions based on personal and global best solutions.
- **Convergence:** Iteratively update particles' positions.
- **Termination:** Continue for a fixed number of iterations or until improvement falls below a threshold.

## Performance Evaluation

Performance is evaluated by comparing the total drilling distance and computational time required for each algorithm. Results are summarized in data frames using the pandas library.

## Visualization

The best drilling paths found by each algorithm are visualized using Matplotlib, comparing the efficiency of the paths generated by different algorithms.

## Results and Discussion

Each algorithm has its strengths and weaknesses. GA gives the best results but is the slowest, while PSO is the fastest but gives the worst results. The choice of algorithm depends on the specific requirements in terms of solution quality and computational efficiency.

## References

1. I. Berninger, “Vehicle Routing Problem on Android/iOS,” Bachelor Thesis, Institute of Computer Science Research Group DPS, University Innsbruck, 2014.
2. A. Homaifar, S. Guan, and G. E. Liepins, “Schema Analysis of the Traveling Salesman Problem Using Genetic Algorithms,” Complex Systems 6, pp. 533-552, 1992.
3. R. Matai, S. Singh, M.L. Mittal, “Traveling Salesman Problem: an Overview of Applications, Formulations, and Solution Approaches,” 2010.
4. T. Narwadi, Subiyanto, “An Application of Traveling Salesman Problem Using the Improved Genetic Algorithm on Android Google Maps,” 2017.
5. M.J: Kochenfender, T.A. Wheeler, Algorithms for Optimization, the MIT Press.
6. https://medium.com/@francis.allanah/travelling-salesman-problem-using-simulated-annealing-f547a71ab3c6.
7. N.M. Razali, J. Geraghty, “Genetic Algorithms Performance Between Different Selection Strategy in Solving TSP,” 2010.
"""
