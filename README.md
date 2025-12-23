# SEIR-Epidemic-Model 🦠

An agent-based epidemiological simulation extending the classic SIR model with exposed states, vaccination, quarantine, and mortality dynamics.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![NetLogo](https://img.shields.io/badge/NetLogo-Agent--Based-green?style=flat)


## 📌 Overview

This NetLogo model simulates disease spread through a population using an **SEIR+ framework** (Susceptible → Exposed → Infected → Recovered), enhanced with:
- **Vaccination** campaigns with adjustable effectiveness
- **Quarantine** protocols based on testing
- **Mortality** dynamics
- **Incubation periods** (exposed but not yet infectious)

The model allows users to explore how different public health interventions affect epidemic outcomes.

## 🔬 Model Structure

### Agent States

| State | Color | Description |
|-------|-------|-------------|
| Susceptible | 🟢 Green | Can be infected |
| Exposed | 🟡 Yellow | Infected but not yet infectious (incubation) |
| Infected | 🔴 Red | Infectious and can spread disease |
| Quarantined | 🟠 Orange | Infected but isolated (cannot spread) |
| Recovered/Immune | ⚪ Gray | Cannot be reinfected |
| Vaccinated | 🔵 Blue | Protected (effectiveness varies) |
| Deceased | ⚫ Black | Dead from infection |

### Disease Progression

```
Susceptible → Exposed → Infected → Recovered/Immune
                            ↓
                        Deceased
```

## ⚙️ Parameters

| Parameter | Range | Description |
|-----------|-------|-------------|
| `num-people` | 20–200 | Population size |
| `initial-infected` | 0–100 | Starting infected agents |
| `infection-chance` | 0–100% | Probability of transmission on contact |
| `incubation-period` | 20–100 ticks | Time in exposed state before becoming infectious |
| `recovery-time` | 50–300 ticks | Time to recover from infection |
| `mortality-rate` | 0–10% | Per-tick probability of death while infected |
| `vaccination-rate` | 0–50 | Agents vaccinated per tick |
| `vaccine-effectiveness` | 50–100% | Probability vaccine grants immunity |
| `quarantine-rate` | 0–100% | Probability infected agents are quarantined |

## 📊 Outputs

- **Demographics vs. Time plot** — Tracks population in each state over time
- **Global counters** — `num-infected`, `num-exposed`, `num-deceased`

## 🚀 Usage

1. Open in **NetLogo 7.0+**
2. Adjust parameters using sliders
3. Click **Setup** to initialize
4. Click **Go** to run simulation
5. Observe dynamics in the view and plot

## 🧪 Experiments to Try

| Scenario | Parameters to Adjust |
|----------|---------------------|
| No intervention baseline | Set `vaccination-rate` and `quarantine-rate` to 0 |
| Aggressive vaccination | Max `vaccination-rate`, high `vaccine-effectiveness` |
| Quarantine-focused response | High `quarantine-rate`, no vaccination |
| High mortality pathogen | Increase `mortality-rate` to 5–10% |
| Long incubation (COVID-like) | Set `incubation-period` to 50–100 |

## 📁 Files

```
SEIR-Epidemic-Model/
└── HW3.nlogox    # NetLogo model file
```

## 🛠️ Requirements

- [NetLogo 7.0+](https://ccl.northwestern.edu/netlogo/download.shtml)

## 📚 Background

This model builds on the classic **SIR compartmental model** (Kermack & McKendrick, 1927) by adding:
- **Exposed compartment** — Captures latent/incubation period
- **Vaccination** — Reduces susceptible population
- **Quarantine** — Reduces effective transmission
- **Mortality** — Removes agents from population

## 📝 License

MIT License — see [LICENSE](LICENSE) for details.

---

*Built for computational modeling coursework exploring dynamic system behaviors in epidemiology.*
