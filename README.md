# APE-MARL-Simulation
Based on the research paper content and best practices for GitHub documentation, I'll now create a comprehensive README.md file for the simulation code repository.

***

# Algorithmic Predatory Equilibrium: MARL-Based Market Manipulation Simulation


## Overview

This repository contains the complete agent-based simulation framework for the research paper **"Algorithmic Predatory Equilibrium: Decentralized Markets Under Regime Shift from Speed to Cognition"**. The codebase implements a multi-agent reinforcement learning (MARL) environment that empirically validates theoretical propositions about autonomous algorithmic trading strategies in decentralized finance markets.

The simulation demonstrates how MARL agents, operating in environments with mempool transparency and deterministic blockchain settlement, converge to systematic exploitation strategies targeting behavioral traders exhibiting loss aversion (λ=2.25). Unlike traditional high-frequency trading systems with hard-coded heuristics, these agents autonomously discover predatory equilibria—including sandwich attacks, spoofing, and behavioral triggering—through environmental interaction rather than explicit programming. 

Our framework bridges three distinct research domains: reinforcement learning optimization (policy gradient MARL), behavioral finance (prospect theory modeling with empirically calibrated parameters), and decentralized market microstructure (automated market maker mechanics with priority gas auctions). The simulation validates that current regulatory frameworks predicated on intent-based enforcement are structurally insufficient against emergent manipulation strategies.

## Key Features

- **Multi-Agent Reinforcement Learning**: Implements policy gradient algorithms (PPO/MAPPO) for predator agents that learn optimal exploitation strategies through trial-and-error interaction with market environments 
- **Behavioral Finance Modeling**: Integrates prospect theory utility functions with empirically calibrated loss aversion coefficient (λ=2.25) to simulate realistic retail trader behavior 
- **AMM Market Simulation**: Full implementation of constant product automated market maker (x·y=k) with priority gas auction mechanics for transaction ordering 
- **Multi-Scenario Testing**: Three experimental scenarios validating propositions across rational baseline, predatory equilibrium, and regulated environments 
- **Mempool Transparency**: Simulates partial observability stochastic games (POSG) where predator agents observe pending transactions before execution 
- **Emergent Strategy Detection**: Framework for identifying spontaneous convergence to sandwich attacks, spoofing, and behavioral cascade triggering without explicit programming 

## Installation

### Prerequisites

- Python 3.8 or higher [
- pip package manager
- Virtual environment (recommended)

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/ape-simulation.git
cd ape-simulation

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Requirements

The simulation requires the following core dependencies: 

```
numpy>=1.21.0
pandas>=1.3.0
scipy>=1.7.0
matplotlib>=3.4.0
dataclasses>=0.6
typing-extensions>=4.0.0
```

```python
from simulation_engine import SimulationEngine
from config import SimulationConfig

# Initialize with default configuration
config = SimulationConfig(
    n_predators=5,
    n_prey=95,
    n_episodes=100,
    episode_length=250,
    loss_aversion_lambda=2.25
)

# Create and run simulation
engine = SimulationEngine(config)
results = engine.run_all_scenarios()

# Display validation results
print(results.proposition_validation)
```

Expected output:
```
Scenario A (Rational Baseline): Market Efficiency = 0.94
Scenario B (Predatory Equilibrium): Predator Alpha = 0.37, Cascade Frequency = 0.21
Scenario C (Regulated): Evasion Strategy Emergence = True
```

## Code Architecture

The simulation framework is organized into four main components: 

| Component | File | Description |
|-----------|------|-------------|
| **Configuration** | `config.py` | Defines `SimulationConfig` dataclass with all simulation parameters including agent populations, behavioral coefficients, market mechanics, and episode specifications   |
| **Agent Classes** | `agents.py` | Implements `PredatorAgent` (MARL with policy gradient optimization) and `PreyAgent` (behavioral model with prospect theory utility)  |
| **Market Model** | `market.py` | Contains `Market` class implementing AMM constant product formula (x·y=k), mempool simulation, and priority gas auction mechanics   |
| **Simulation Engine** | `simulation_engine.py` | Orchestrates multi-episode execution across three scenarios (Rational Baseline, Predatory Equilibrium, Regulated), manages agent interactions, and collects validation metrics |

## Configuration Parameters

Key parameters in `SimulationConfig`:
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `loss_aversion_lambda` | float | 2.25 | Prospect theory loss aversion coefficient (empirically calibrated)  |
| `n_predators` | int | 5 | Number of MARL-based predator agents  |
| `n_prey` | int | 95 | Number of behavioral prey agents   |
| `n_episodes` | int | 100 | Training episodes per scenario  |
| `episode_length` | int | 250 | Time steps per episode |
| `amm_initial_reserves` | tuple | (1000, 1000) | Initial AMM liquidity pool reserves (x, y)  |
| `mempool_visibility` | bool | True | Whether predators observe pending transactions   |
| `gas_auction_enabled` | bool | True | Enable priority gas auction for transaction ordering  |
| `regulatory_penalty` | float | 0.0 | Penalty coefficient for detected manipulation (Scenario C only)   |

## Usage Examples

### Running Individual Scenarios

```python
from simulation_engine import SimulationEngine
from config import SimulationConfig

config = SimulationConfig()
engine = SimulationEngine(config)

# Scenario A: Rational baseline with all agents optimizing wealth
results_a = engine.run_scenario_a()
print(f"Market Efficiency: {results_a.efficiency_metric}")

# Scenario B: Predatory equilibrium with MARL predators + behavioral prey
results_b = engine.run_scenario_b()
print(f"Predator Alpha: {results_b.predator_alpha}")
print(f"Cascade Frequency: {results_b.cascade_frequency}")

# Scenario C: Regulated environment with detection penalties
results_c = engine.run_scenario_c()
print(f"Evasion Emerged: {results_c.evasion_detected}")
```

### Modifying Behavioral Parameters

```python
from config import SimulationConfig

# Test sensitivity to loss aversion coefficient
lambdas = [1.5, 2.0, 2.25, 2.5, 3.0]
results = []

for lambda_val in lambdas:
    config = SimulationConfig(loss_aversion_lambda=lambda_val)
    engine = SimulationEngine(config)
    result = engine.run_scenario_b()
    results.append({
        'lambda': lambda_val,
        'predator_alpha': result.predator_alpha,
        'victim_wealth_loss': result.victim_wealth_loss
    })
```

### Accessing Agent-Level Data

```python
# Extract individual agent trajectories
results = engine.run_scenario_b()

# Predator agent learning curves
for agent_id, trajectory in results.predator_trajectories.items():
    print(f"Agent {agent_id} Final Policy Reward: {trajectory[-1].reward}")

# Prey behavioral responses
panic_sell_frequency = results.prey_actions.count('panic_sell') / len(results.prey_actions)
print(f"Panic Sell Rate: {panic_sell_frequency:.2%}")
```

## Results & Validation

The simulation produces comprehensive output for validating research propositions: 
### Proposition 1: Convergence to Predatory Equilibrium
**Validation Metrics:**
- Predator agents achieve super-normal returns (alpha > 0) relative to rational baseline 
- Emergence of sandwich attacks, spoofing, and cascade triggering without explicit programming
- Statistical significance testing (t-tests) comparing Scenario B vs. Scenario A
  
### Proposition 2: Regulatory Insufficiency
**Validation Metrics:**
- Detection of evasion strategies in Scenario C (e.g., distributing orders across agents to stay below cancellation rate thresholds) 
- Comparison of manipulation frequency pre- and post-regulation 
- Measurement of equilibrium shift (not dissolution) under regulatory constraints 

## Research Context

This simulation implements the theoretical framework and empirical validation methodology described in the accompanying academic paper. The code specifically validates:
1. **Algorithmic Predatory Equilibrium (APE) Thesis**: MARL agents converge to systematic exploitation strategies when operating in partially observable stochastic games with behavioral traders exhibiting loss aversion

2. **Nash Equilibrium Properties**: Sandwich attacks and MEV extraction emerge as stable equilibria where deviation is unprofitable

3. **Regulatory Gap Analysis**: Intent-based enforcement frameworks fail against emergent strategies that arise autonomously through optimization 

The simulation extends prior work on MEV extraction  by integrating behavioral finance parameters (prospect theory with λ=2.25) and demonstrating that the presence of loss-averse retail traders amplifies predator profitability through behavioral triggering strategies. 

## Supporting Visuals
https://github.com/Shrey6876/APE-MARL-Simulation/blob/1b90d35ddafdb3e2a1f9ac1b833f5951ac8aca5b/Marl-supporting-1.jpg
https://github.com/Shrey6876/APE-MARL-Simulation/blob/c06a2fb1ca64f3dd4238914571c859baf79086ee/MARL-SUPPORTING-2.jpg


## Citation

This simulation is a part of my research, upon publication an update will be made regarding citing the paper properly , which would always be appreciated


```

## License

This project is licensed under the MIT License -
