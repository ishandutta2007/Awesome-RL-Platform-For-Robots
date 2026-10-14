# Awesome-RL-Platform-For-Robots

# Top RL Platforms for Robots Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on GPU-Accelerated Training, Distributed RL & Robot Learning Workflows*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Reinforcement Learning Platforms for Robots**. These tools provide the training infrastructure, algorithm implementations, and experiment management needed to learn robot control policies — from massively parallel GPU simulation to distributed cloud training and reproducible research pipelines.

**Examples** include NVIDIA Isaac Gym, Ray RLlib, Stable-Baselines3, Weights & Biases, CleanRL, TorchRL, Tianshou, ElegantRL, Acme (DeepMind), and Gymnasium Robotics (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, custom algorithm development, and transparent training workflows — ideal for robotics researchers, RL practitioners, and teams building robot learning infrastructure.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Weights & Biases](https://wandb.ai/)**  
  Experiment tracking and ML observability platform for RL training runs. Logs metrics, hyperparameters, videos, and system stats across distributed jobs. Free for personal use, with academic plans available for students and researchers. Serverless Inference includes included credits on Free, Pro, and Academic plans, with usage-based billing beyond included limits .

- **[NVIDIA Isaac Gym](https://developer.nvidia.com/isaac-gym)**  
  NVIDIA's GPU-accelerated physics simulation for RL, now succeeded by Isaac Lab. Enables thousands of parallel environments on a single GPU, eliminating CPU-GPU data transfer bottlenecks by keeping physics stepping, observation computation, and action application entirely on device . Access via developer program.

- **[Ray RLlib (Anyscale)](https://www.anyscale.com/)**  
  Commercial support and managed deployment for RLlib, the industry-grade distributed RL library. Anyscale provides hosted Ray clusters for scaling RL workloads from laptop to cluster.

## Open-Source GitHub Projects

- **[Ray RLlib](https://github.com/ray-project/ray)**  
  **Industry-grade, scalable reinforcement learning library** for production workloads with a unified API across multi-agent, offline, and externally connected simulators . New API stack (Ray 2.40+) uses `AlgorithmConfig` and `Algorithm` classes with `EnvRunnerGroup` and `LearnerGroup` for elastic scaling from one core to thousands . Supports PettingZoo, Gymnasium, Atari, and MuJoCo environments. Apache 2.0 licensed.

- **[Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3)**  
  **Reliable PyTorch implementations of RL algorithms** with a scikit-learn-like API. Designed for reproducibility and as a baseline for research. Includes RL Baselines3 Zoo for trained agents and hyperparameter tuning. Quick example: `PPO("MlpPolicy", "CartPole-v1").learn(10_000)` . MIT licensed.

- **[CleanRL](https://github.com/vwxyzjn/cleanrl)**  
  **High-quality single-file implementations** of deep RL algorithms. Every algorithm variant is contained in one standalone file (e.g., `ppo_atari.py` is 340 lines with all PPO details). Not meant to be imported — designed for understanding and prototyping advanced features. Benchmarked across 7+ algorithms and 34+ games. Tensorboard logging, local reproducibility, and W&B integration .

- **[TorchRL](https://github.com/pytorch/rl)**  
  **PyTorch-native RL library** with explicit TensorDict-based data contracts. Provides modular actors, critics, losses, replay buffers, and trainers. Supports PPO, SAC, DQN, TD3, REDQ, IQL, CQL, Decision Transformer, Dreamer, MAPPO, and more . Used in robotics, control, multi-agent RL, and drug discovery. MIT licensed .

- **[Tianshou](https://github.com/thu-ml/tianshou)**  
  **Modular RL library** with a clean policy abstraction. Policy classes expose `forward()`, `process_fn()`, `learn()`, and `update()` methods with explicit training/collecting/updating states . Includes prioritized and vectorized replay buffers. Popular in Chinese ML community. MIT licensed.

- **[ElegantRL](https://github.com/AI4Finance-Foundation/ElegantRL)**  
  **Lightweight, cloud-native RL library** with <1,000 lines of core code. Claims greater stability than Stable-Baselines3 and higher efficiency than Ray RLlib in many single-GPU/multi-GPU cases . Supports DDPG, TD3, SAC, PPO, REDQ, DQN, QMIX, MADDPG, MAPPO, and MATD3. Scales to hundreds/thousands of GPUs via ElegantRL-Podracer. Integrates with Isaac Gym for massively parallel simulation.

- **[Acme (DeepMind)](https://github.com/google-deepmind/acme)**  
  **Research framework for RL** with modular acting and learning components . Agents expose `select_action`, `observe`, and `update` methods. Supports single-process and distributed agent configurations with identical components . Designed as reference implementations and baselines for novel research. Apache 2.0 licensed.

- **[Gymnasium Robotics](https://github.com/Farama-Foundation/Gymnasium-Robotics)**  
  **Collection of RL robotic environments** using the Gymnasium API and MuJoCo physics. Includes Fetch (7-DoF arm manipulation), Shadow Dexterous Hand (24-DoF hand with 92 touch sensors), Maze (D4RL environments with Ant and point-mass agents), Adroit Arm, Franka Kitchen, and MaMuJoCo (multi-agent MuJoCo) . `pip install gymnasium-robotics`. MIT licensed.

- **[Isaac Lab](https://github.com/isaac-sim/IsaacLab)**  
  Successor to Isaac Gym, built on NVIDIA Isaac Sim with GPU-accelerated physics and photorealistic rendering for RL training.

- **[Brax](https://github.com/google/brax)**  
  Google's differentiable physics engine for JAX. Enables gradient-based optimization and massively parallel RL on TPUs/GPUs.

- **[MuJoCo](https://github.com/google-deepmind/mujoco)**  
  Physics engine underlying Gymnasium Robotics. The gold standard for contact-rich manipulation and RL research. Apache 2.0 licensed.

### Additional Strong Open-Source Options

- **[CORL](https://github.com/corl-team/CORL)** — Clean single-file implementations of offline RL algorithms, sharing CleanRL's design philosophy .
- **[RL Baselines3 Zoo](https://github.com/DLR-RM/rl-baselines3-zoo)** — Training framework, hyperparameter tuning, and trained agents for Stable-Baselines3 .
- **[PettingZoo](https://github.com/Farama-Foundation/PettingZoo)** — Multi-agent RL environments compatible with RLlib, Tianshou, and Gymnasium-Robotics.
- **[D4RL](https://github.com/Farama-Foundation/D4RL)** — Datasets for offline RL, now refactored into Gymnasium-Robotics .
- **Minari** — Dataset format and tools for offline RL and RL datasets .

**Frameworks for building custom systems**: Combine **Isaac Gym** or **Isaac Lab** for massively parallel GPU simulation, **Ray RLlib** or **ElegantRL** for distributed training, **CleanRL** for understanding algorithm internals, **TorchRL** for PyTorch-native modular RL, and **Gymnasium Robotics** for standardized robot environments to build a complete self-hosted robot RL stack.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- RL platforms for robots involve training policies that will control physical systems. Sim-to-real gap validation, safety constraints, and extensive testing in simulation are required before hardware deployment. Incorrect policies can cause equipment damage or injury.
- Self-hosted open-source solutions require proper GPU infrastructure, experiment tracking, and reproducibility practices.

---

**Made for robotics researchers, RL practitioners, graduate students, and developers building robot learning platforms.**  
Let's make RL for robots more open, reproducible, and accessible.
