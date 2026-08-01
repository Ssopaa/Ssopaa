# Task-Oriented Communication — Power & Frequency Allocation

> AI & Mobile Lab, Dept. of EE, Konkuk University · Industry-Academia Research (2025)

## Overview

Industry-academia research on deep-learning-based resource allocation for D2D wireless networks. The goal: allocate **transmit power** and **frequency** across links to maximize sum rate while controlling interference — replacing slow exhaustive search with fast, learned allocators.

## Frequency allocation — algorithm comparison

A comparative study of frequency-allocation strategies for D2D pairs, each implemented from scratch and benchmarked against an exhaustive **Full Search** on average sum-rate.

| Method | Avg sum-rate (bps/Hz) | vs Full Search |
|--------|-----------------------|----------------|
| **Genetic Algorithm** | **58.18** | **99.90%** |
| Game Theory (Best-Response) | 57.78 | 99.21% |
| DNN (learned allocator) | 56.06 | 96.26% |
| Hungarian Matching | 48.32 | 82.97% |
| Graph Coloring (greedy) | 46.45 | 79.75% |

- **Genetic Algorithm** — allocation encoded as per-pair frequency genes; sum-rate fitness, elitist selection, single-point crossover, mutation. Came within **0.1%** of exhaustive search.
- **Game Theory** — best-response dynamics converging toward a Nash equilibrium.
- **DNN** — learned allocator (softmax over frequencies), trades a little optimality for fast inference.
- **Hungarian Matching** — assignment-problem formulation via `scipy.optimize.linear_sum_assignment`.
- **Graph Coloring** — interference graph (nodes = pairs, edges = interference above threshold), greedy coloring = frequency assignment.

## Joint power–frequency allocation

Extending beyond frequency-only assignment, this track **jointly optimizes power and frequency** together.

**Method — joint DNN (self-designed).** Rather than deciding power and frequency separately, the network treats each link's assignment as a **single discrete decision space** of (frequency × power-level) combinations: a softmax yields the probability of each combined case, the model is trained with a differentiable *expected* sum-rate objective, and the highest-probability case is selected at inference.

**Result.** The joint DNN reached **97.6% of the exhaustive Full-Search optimum** on average sum-rate (52.63 vs 53.84 bps/Hz) — near-optimal, and far above the random baselines:

| Method | Avg sum-rate (bps/Hz) | vs Full Search |
|--------|-----------------------|----------------|
| Full Search (optimal) | 53.84 | 100% |
| **DNN (joint, self-designed)** | **52.63** | **97.6%** |
| Random frequency (max power) | 48.83 | 90.7% |
| Full random | 34.17 | 63.5% |

Graph-based variants (**ResourceAllocationGNN**, **JCPGNN**) were also explored against a Full-Search + WMMSE hybrid upper bound.

## My role

Designed the joint DNN architecture and implemented the training/evaluation pipelines (TensorFlow/PyTorch), all five frequency-allocation methods, and the GNN allocators (ResourceAllocationGNN / JCPGNN), running the comparative benchmarks against Full Search (and the FS+WMMSE hybrid) — including population/generation sweeps for the genetic algorithm.

## Tech stack

`Python` · `TensorFlow` · `PyTorch` · `NumPy` · `scikit-learn`
