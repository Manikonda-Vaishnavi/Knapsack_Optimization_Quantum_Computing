# Optimization of Knapsack Algorithm using D-Wave Quantum Computing
This project implements the 0/1 Knapsack Problem using D-Wave's quantum annealer. It formulates the combinatorial optimization task as a QUBO (Quadratic Unconstrained Binary Optimization) model to leverage quantum computing power for solving NP-hard problems efficiently.

#  What is the Knapsack Problem?
The 0/1 Knapsack Problem is a classic problem in combinatorial optimization. Given a set of items, each with a weight and a value, the goal is to determine the most valuable subset of items to include in a knapsack without exceeding its weight capacity.

Formally:

yaml
Copy
Edit
Maximize:    ∑(value[i] * x[i])
Subject to:  ∑(weight[i] * x[i]) <= capacity
Where:       x[i] ∈ {0, 1}
#  Quantum Computing with D-Wave
To solve this problem using D-Wave, we:

Encode the knapsack constraints and objective function into a QUBO form.

Submit the QUBO to D-Wave’s quantum annealer using the DWaveSampler and EmbeddingComposite.

Interpret the low-energy solutions returned by the quantum hardware to find the optimal item selection.

#  How It Works
Define item weights and values.

Convert the knapsack problem into a QUBO matrix that reflects:

Maximizing total value.

Penalizing solutions that exceed the weight capacity.

Send the QUBO to D-Wave’s quantum sampler.

Extract the best sample (solution) from the returned results.

# Requirements
Python 3.x

dwave-system

numpy

dimod

Install via pip:

bash
Copy
Edit
pip install dwave-ocean-sdk
📁 Project Structure
bash
Copy
Edit
.
├── knapsack_quantum.py      # Main implementation file
├── README.md                # Project documentation
└── requirements.txt         # List of required libraries
📸 Example Output
Given:

Items: [value: 8, weight: 2], [value: 10, weight: 4], [value: 15, weight: 5]

Knapsack capacity: 6

The quantum annealer may output:

yaml
Copy
Edit
Selected items: [1, 0, 1]
Total value: 23
Total weight: 7 (penalized)
(Quantum solutions may occasionally violate constraints unless heavily penalized.)

# Conclusion
This project demonstrates how quantum computing can be applied to classical optimization problems like the Knapsack Problem. By formulating the task into a QUBO, we utilize D-Wave's quantum annealer to efficiently search for high-quality solutions. Although quantum devices are still maturing, this implementation offers a glimpse into the future of optimization using quantum resources.

Quantum optimization is not just a theoretical curiosity—it’s a practical tool for solving real-world problems with massive solution spaces.
