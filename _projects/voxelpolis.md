---
title: 'An AlphaGo Moment for Urban Simulation'
subtitle: 'Training Reinforcement Learning Agents on the Authentic Micropolis Engine'
# featured_image: "/assets/images/voxelpolis/work_in_process_1.png"
---

![pic_1](/assets/images/voxelpolis/work_in_process_1.png)

![pic_2](/assets/images/voxelpolis/work_in_process_2.png)

### Abstract

The release of Micropolis—the open-source version of the original 1989 SimCity—provided a rare opportunity to access one of the earliest and most influential urban simulation engines. 
This work presents a modern revival of Micropolis through the development of a fully headless simulation core, decoupled from its legacy GUI. By exposing the engine via Python bindings and a callback-based rendering API,
we enable seamless integration with contemporary frameworks, including FLTK for desktop visualization, SDL2 for mobile deployment, and IrrlichtMt for future 3D voxel rendering.

Drawing inspiration from AlphaGo's breakthrough in mastering Go through self-play and reinforcement learning, we transform Micropolis into a reinforcement learning environment. Using Proximal Policy Optimization (PPO), agents are trained to act as "AI mayors," learning to place zones, manage infrastructure, and respond to emergent dynamics such as RCI demand, land value propagation, crime, pollution, and disasters. Preliminary results demonstrate agents achieving significantly higher population growth and long-term stability compared to random or heuristic baselines, uncovering zoning strategies that exploit subtle feedback loops in the original simulation.

Beyond performance, the project serves as a bridge between digital heritage preservation and contemporary computational urban design.

The headless core facilitates large-scale AI experiments, educational tools. By making the authentic SimCity engine accessible to modern machine learning workflows, this work represents an "AlphaGo moment" for urban simulation—demonstrating how classic rule-based systems can yield superhuman planning capabilities when paired with reinforcement learning.
This paper discusses the technical architecture, training methodology, observed emergent behaviors, and implications for AI-assisted urban planning education and research.
