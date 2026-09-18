# EcoRoute: Green Logistics & Emission-Aware Dispatcher

**Course Name:** Programming in Java  
**Course Code:** CSE2006  
**Student Name:** Ankit Singh  
**Registration No.:** 25BAI11247  
**Faculty Mentor:** Komarasamy G.  

---

## Overview of the Project

The freight logistics industry accounts for roughly a quarter of worldwide greenhouse gas emissions, primarily caused by medium and heavy haulage vehicles. Conventional navigation systems choose routes based on linear distance or transit time. For a fully loaded freight truck, however, traversing steep uphill road gradients burns significantly more fuel than traveling along slightly longer, flat bypasses.

**EcoRoute** is an emission-first logistics optimization tool developed in Java 17+. Instead of relying on static distances, EcoRoute models road networks as dynamic graphs. Edge weights are dynamically computed in kilograms of carbon dioxide ($kg\ CO_2$) using vehicle tare weight, consignment payload, road incline angle, and baseline engine fuel rates. The system runs an emission-weighted Dijkstra search to pinpoint the lowest-emission route and prints an automated audit manifest measuring real-world savings against traditional shortest-distance routing.

---

## Features

- **Dynamic Emission Physics Engine:** Evaluates road slope resistance and vehicle load on every edge, calculating fuel burn ($L$) and carbon emissions ($kg\ CO_2$) on the fly.
- **Eco-Routing Pathfinding:** Uses a custom binary min-heap Priority Queue to execute Dijkstra traversal optimized for minimal total carbon footprint.
- **Automated Audit Manifest:** Runs a baseline shortest-distance routing calculation in parallel, showing a side-by-side comparison of net fuel and carbon saved.
- **Payload Capacity Validation:** Enforces strict vehicle capacity limits using a custom `OverloadException` to reject overweight freight before dispatch.
- **Disconnected Node Detection:** Gracefully handles unreachable delivery hubs via a custom `PathNotFoundException`.

---

## Technologies/Tools Used

- **Programming Language:** Java (JDK 17 or higher)
- **Build System:** Apache Maven / Standard javac CLI
- **Testing Framework:** JUnit 5 (Jupiter Engine)
- **Version Control:** Git & GitHub
- **IDE:** Visual Studio Code

---

## Steps to Install & Run the Project

### Prerequisites
- Install Java Development Kit (JDK 17 or later).
- Verify installation:
  ```bash
  java -version
  javac -version