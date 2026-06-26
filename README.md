# Design and Analysis of an Accuracy Configurable Fast Approximation Recursive Multiplier (FARM)

**Status:** RTL Code and Physical Design files are currently withheld due to academic publication purpose.

## 📌 Project Overview
[cite_start]Error-resilient applications in domains like machine learning and signal processing require approximate arithmetic circuits optimized for speed, power, and area[cite: 28]. [cite_start]This project introduces a 32-bit Fast Accurate Recursive Multiplier (FARM) integrated with a Fast Accuracy Reconfigurable Adder (FARA)[cite: 29]. 

[cite_start]The architecture features dynamic reconfigurability, allowing the system to switch between a fully exact, error-free mode and multiple levels of approximation at run-time[cite: 31, 46]. [cite_start]By utilizing a hierarchical divide-and-conquer approach and recursive addition of partial products, the design drastically cuts down the area overhead typically associated with complex reconfigurable multipliers[cite: 58, 113].

## 🛠️ VLSI Physical Design Flow
[cite_start]The project encompasses a complete front-to-back digital physical design flow targeting a **45nm CMOS technology node**[cite: 49]. 

* [cite_start]**Front-End Synthesis:** Cadence Genus was utilized to generate structural netlists and extract baseline Area, Power, and Delay metrics[cite: 50].
* [cite_start]**Back-End Physical Design:** Cadence Innovus was utilized for Floorplanning, Power Planning, Placement, Clock Tree Synthesis (CTS), Routing, and Metal Fill to achieve a tapeout-ready layout[cite: 51, 1857].
* [cite_start]**Verification:** A robust SystemVerilog Layered Testbench was developed for automated stimulus generation and self-checking across randomized test batches[cite: 48].

## 📊 Key Results & Metrics

[cite_start]The design was fully verified functionally and optimized through the physical layout phase[cite: 68, 1823].

### Performance & Accuracy
* [cite_start]**Speedup:** Delivered a speedup of over 30% (Data arrival time reduced from 9851.6 ps to 6904.1 ps) against the exact mode when configured for maximum approximation[cite: 32, 1239, 1240].
* [cite_start]**Error Control:** Exact mode operates with zero errors, preventing arithmetic overflow by utilizing a full 64-bit output path[cite: 654, 1828].

### ASIC Synthesis Results (45nm)
* [cite_start]**Total Power:** ~3.59 mW (dominated by dynamic switching power)[cite: 71, 1174].
* [cite_start]**Base Synthesis Area:** 9428.26 µm²[cite: 69].

### Physical Layout & Floorplanning
* [cite_start]**Core Area:** 10993.76 µm²[cite: 73].
* [cite_start]**Core Utilization:** 79.97% (Optimized with a core isolation value of 0.8)[cite: 74, 1508].
* **Die Dimensions:** Height = 110.2 µm | [cite_start]Width = 115.2 µm[cite: 1552, 1556].
* [cite_start]**DRC & CTS:** The final routed layout passed all Design Rule Checks (0 errors) and maintained a positive setup slack (0.002 ns) at a targeted 500 MHz frequency[cite: 1592, 1697, 1853].

## 📸 Layout Highlights
*(Add your final routed layout images and floorplan screenshots here from the `physical_design` folder)*
- `![Final Routed Layout](physical_design/final_routed_layout.png)`
- `![Approximate Waveforms](docs/simulation/approximate_mode_waveforms.png)`
