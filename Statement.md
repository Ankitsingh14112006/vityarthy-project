#EcoRoute Logistics Dispatcher

## Problem Statement
Standard routing algorithms optimize paths based strictly on shortest linear distance or travel time. In freight logistics, this overlooks fuel penalties caused by vehicle payload mass and road elevation gradients. A heavy truck ascending steep highway gradients can burn up to 40% to 60% more fuel than it would on a slightly longer, flatter valley bypass. Fleet operators lack an automated system that models vehicle dynamics and road slopes into algorithmic routing choices, leading to unnecessary fuel costs and higher Scope 1 greenhouse gas emissions.

## Scope of the Project
  EcoRoute is a modular Java software system that models logistics networks as directed graphs. It calculates dynamic edge weights based on vehicular mechanical work and slope angles rather than static road lengths. The project scope encompasses:
- Modeling delivery nodes and road segments with distance and percent elevation gradient.
- Dynamic carbon and fuel burn calculation based on gross vehicle mass and slope.
- Priority-queue graph pathfinding for green route determination.
- Dispatch validation and comparative audit manifest generation.

## Target Users
- **Fleet Dispatchers & Operations Managers:** Logistics professionals planning freight transit while controlling fuel overhead.
- **Sustainability & Compliance Auditors:** Teams tracking, reporting, and minimizing supply chain carbon footprints.
- **Commercial Freight Operators:** Transport businesses operating heavy cargo vehicles across varied terrain.

## High-Level Features
- **Vehicle & Cargo Configuration:** Ingestion and validation of truck profiles (tare weight, max capacity, fuel burn factor) and delivery consignments.
- **Dynamic Physics Engine:** Real-time computation of fuel burn (L) and carbon emissions (kg CO2) accounting for gradient resistance and engine idle baselines.
- **Emission-Aware Dijkstra Routing:** Optimal path determination using a binary min-heap Priority Queue to minimize total emissions.
- **Comparative Benchmark Manifest:** Automated side-by-side analysis demonstrating fuel and carbon saved compared to standard shortest-distance routing.
- **Fault-Tolerant Exception Handling:** Custom checked exceptions (OverloadException, PathNotFoundException) protecting against operational errors.