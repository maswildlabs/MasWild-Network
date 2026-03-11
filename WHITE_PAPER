# WHITE_PAPER.md

## Project: Mas Wild Labs Network Architecture
**Author:** Mas Wild Labs  
**Ecosystem:** Ubiquiti UniFi  
**Status:** Phase 1 (Physical) Implemented | Phase 2 (Logical) Planned  

---

## 1. Executive Summary
This document outlines the design and implementation of a converged network infrastructure optimized for high-throughput virtualization (**Proxmox VE**), GPU-accelerated compute nodes (**NVIDIA**), and professional hardware testing (**Spectrio/EngageDSX**). 

The architecture leverages a **Cloud Gateway Ultra** and a **2.5GbE core** to ensure data velocity remains unhindered by traditional Gigabit bottlenecks, while a planned VLAN strategy provides micro-segmentation for security and testing.

---

## 2. Network Topology (Visual)
The following diagram illustrates the physical and logical flow of the Mas Wild Labs environment. GitHub will automatically render this text into a visual flowchart:

```mermaid
graph TD
    subgraph Internet_Edge
        ISP[ATT Fiber Router] -- IP Passthrough --> UCG[Cloud Gateway Ultra]
    end

    subgraph Zone_A_Desk_2.5G
        UCG -- Direct Connect --> Flex2.5[Switch Flex 2.5G]
        Flex2.5 --- PC[Workstation PC]
        Flex2.5 --- Prox[Proxmox VE]
    end

    subgraph Zone_B_Lab_Hub
        UCG -- "20ft Cat6 Trunk" --> Lite8[Switch Lite 8 PoE]
        Lite8 --- WAP[Swiss Army Knife Ultra]
        Lite8 --- Flex1[Switch Flex]
        Flex1 --- NV[NVIDIA Nodes]
        Flex1 --- Spec[Spectrio / EngageDSX]
    end

    style Flex2.5 fill:#f96,stroke:#333
    style UCG fill:#3498db,stroke:#333,color:#fff
