# Fast Partially-Ordered Graph Isomorphisms, Arithmetic, and Visualizations

This repository contains a C++ implementation of algorithms for computing canonical labels of partially-ordered graphs, specifically designed for applications in mathematical physics with scattering diagrams. The program efficiently generates graph coefficients and provides a data format for doing arithmetic operations over partially-ordered graphs, with output compatible with Mathematica for further analysis and clear visualization.

## Installation and Compilation

You merely need to have a C++ compiler and this repository downloaded. As an example of how to use this isomorphism program, we provide `chen-strichartz_run.cpp`, which computes Chen-Strichartz coefficients for scattering diagrams up to a specified degree in Planck's constant.

# Chen-Strichartz Formula for the Magnus Expansion

### Compilation

```bash
g++ -std=c++17 -o chen-strichartz_run chen-strichartz_run.cpp graph_visualizer.cpp
```

## Usage

### Basic usage (terminal output):
```bash
./chen-strichartz_run --degree 2
./chen-strichartz_run --degree 3
```

### Additional options:
```bash
# Specify loop order (default: 1)
./chen-strichartz_run --degree 3 --loop-order 2

# Enable/disable plus-minus symmetry (default: true)
./chen-strichartz_run --degree 2 --bicolored false

# Combined example
./chen-strichartz_run --degree 4 --loop-order 1 --bicolored true --mathematica output.m
```

## Files

- `chen-strichartz_run.cpp` - Main program
- `graph_visualizer.cpp` - Graph parsing and visualization functions  
- `graph_visualizer.hpp` - Header file for visualization functions

# TODO

- [ ] Optimize memory usage
- [ ] Re-use computations for efficiency 
- [ ] Implement graph databases storage for caching big reusable computations and for later analysis
- [ ] Add OpenMP integration; think about SIMD
- [ ] Make sure algorithms, data structures, and keyword (those affecting efficiency, such as inline, const, &) usage is optimal
- [ ] Create detailed documentation for each overtly-user-facing function in the codebase
- [ ] Implement the availability to read graphs from files, in a few different formats.
- [ ] Find further applications within mathematics, physics, and computer science.
- [ ] Write detailed insights into the algorithm's operation.
- [ ] Clean up the codebase.
- [ ] Create nice visualizations of the output.
- [ ] PRIORITY OBJECTIVE : You have multiple copies of almost every file. Compress them by deleting extra stuff and utilizing configuration options. Also, put all the tests in one file. Consider adding a main script so configuration is easier. Also, add a Makefile.