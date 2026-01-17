# APE-MARL-Simulation
Based on the research paper content and best practices for GitHub documentation, I'll now create a comprehensive README.md file for the simulation code repository.

***

# Algorithmic Predatory Equilibrium: MARL-Based Market Manipulation Simulation


## Overview

This repository contains the complete agent-based simulation framework for the research paper **"Algorithmic Predatory Equilibrium: Decentralized Markets Under Regime Shift from Speed to Cognition"**. The codebase implements a multi-agent reinforcement learning (MARL) environment that empirically validates theoretical propositions about autonomous algorithmic trading strategies in decentralized finance markets. [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

The simulation demonstrates how MARL agents, operating in environments with mempool transparency and deterministic blockchain settlement, converge to systematic exploitation strategies targeting behavioral traders exhibiting loss aversion (λ=2.25). Unlike traditional high-frequency trading systems with hard-coded heuristics, these agents autonomously discover predatory equilibria—including sandwich attacks, spoofing, and behavioral triggering—through environmental interaction rather than explicit programming. [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

Our framework bridges three distinct research domains: reinforcement learning optimization (policy gradient MARL), behavioral finance (prospect theory modeling with empirically calibrated parameters), and decentralized market microstructure (automated market maker mechanics with priority gas auctions). The simulation validates that current regulatory frameworks predicated on intent-based enforcement are structurally insufficient against emergent manipulation strategies. [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

## Key Features

- **Multi-Agent Reinforcement Learning**: Implements policy gradient algorithms (PPO/MAPPO) for predator agents that learn optimal exploitation strategies through trial-and-error interaction with market environments [docs.github](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
- **Behavioral Finance Modeling**: Integrates prospect theory utility functions with empirically calibrated loss aversion coefficient (λ=2.25) to simulate realistic retail trader behavior [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- **AMM Market Simulation**: Full implementation of constant product automated market maker (x·y=k) with priority gas auction mechanics for transaction ordering [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- **Multi-Scenario Testing**: Three experimental scenarios validating propositions across rational baseline, predatory equilibrium, and regulated environments [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- **Mempool Transparency**: Simulates partial observability stochastic games (POSG) where predator agents observe pending transactions before execution [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- **Emergent Strategy Detection**: Framework for identifying spontaneous convergence to sandwich attacks, spoofing, and behavioral cascade triggering without explicit programming [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

## Installation

### Prerequisites

- Python 3.8 or higher [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
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

The simulation requires the following core dependencies: [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

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

The simulation framework is organized into four main components: [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

| Component | File | Description |
|-----------|------|-------------|
| **Configuration** | `config.py` | Defines `SimulationConfig` dataclass with all simulation parameters including agent populations, behavioral coefficients, market mechanics, and episode specifications  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| **Agent Classes** | `agents.py` | Implements `PredatorAgent` (MARL with policy gradient optimization) and `PreyAgent` (behavioral model with prospect theory utility)  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| **Market Model** | `market.py` | Contains `Market` class implementing AMM constant product formula (x·y=k), mempool simulation, and priority gas auction mechanics  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| **Simulation Engine** | `simulation_engine.py` | Orchestrates multi-episode execution across three scenarios (Rational Baseline, Predatory Equilibrium, Regulated), manages agent interactions, and collects validation metrics  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |

## Configuration Parameters

Key parameters in `SimulationConfig`: [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `loss_aversion_lambda` | float | 2.25 | Prospect theory loss aversion coefficient (empirically calibrated)  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `n_predators` | int | 5 | Number of MARL-based predator agents  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `n_prey` | int | 95 | Number of behavioral prey agents  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `n_episodes` | int | 100 | Training episodes per scenario  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `episode_length` | int | 250 | Time steps per episode  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `amm_initial_reserves` | tuple | (1000, 1000) | Initial AMM liquidity pool reserves (x, y)  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `mempool_visibility` | bool | True | Whether predators observe pending transactions  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `gas_auction_enabled` | bool | True | Enable priority gas auction for transaction ordering  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |
| `regulatory_penalty` | float | 0.0 | Penalty coefficient for detected manipulation (Scenario C only)  [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx) |

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

The simulation produces comprehensive output for validating research propositions: [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

### Proposition 1: Convergence to Predatory Equilibrium
**Validation Metrics:**
- Predator agents achieve super-normal returns (alpha > 0) relative to rational baseline [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- Emergence of sandwich attacks, spoofing, and cascade triggering without explicit programming [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- Statistical significance testing (t-tests) comparing Scenario B vs. Scenario A [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

### Proposition 2: Regulatory Insufficiency
**Validation Metrics:**
- Detection of evasion strategies in Scenario C (e.g., distributing orders across agents to stay below cancellation rate thresholds) [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- Comparison of manipulation frequency pre- and post-regulation [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)
- Measurement of equilibrium shift (not dissolution) under regulatory constraints [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)


## Research Context

This simulation implements the theoretical framework and empirical validation methodology described in the accompanying academic paper. The code specifically validates: [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

1. **Algorithmic Predatory Equilibrium (APE) Thesis**: MARL agents converge to systematic exploitation strategies when operating in partially observable stochastic games with behavioral traders exhibiting loss aversion [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

2. **Nash Equilibrium Properties**: Sandwich attacks and MEV extraction emerge as stable equilibria where deviation is unprofitable [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

3. **Regulatory Gap Analysis**: Intent-based enforcement frameworks fail against emergent strategies that arise autonomously through optimization [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)

The simulation extends prior work on MEV extraction  by integrating behavioral finance parameters (prospect theory with λ=2.25) and demonstrating that the presence of loss-averse retail traders amplifies predator profitability through behavioral triggering strategies. [ppl-ai-file-upload.s3.amazonaws](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/collection_a644698b-ce69-46fb-b193-dd178a43dad8/3e03ca7d-6640-4430-8ba9-036e1f8672e9/Algorithmic-Predatory-Equilibrium.docx)



## Citation

This simulation is a part of my research, upon publication an update will be made regarding citing the paper properly , which would always be appreciated


```

## License

This project is licensed under the MIT License -
