---
layout: single
title: "Research"
permalink: /research/
author_profile: true
excerpt: "Research projects in networked VR, wireless systems, and transport protocols"
---

My research develops practical network mechanisms for immersive and interactive applications. Across these projects, I combine application-level quality signals with transport and wireless decisions, then evaluate the resulting systems through implementation and measurement.

## Efficient streaming of immersive content over Wi-Fi

**Ph.D. thesis research · Purdue University · 2022–present**

My thesis develops cross-layer scheduling mechanisms for immersive content delivery over Wi-Fi. The central idea is to expose application-level perceptual utility and latency requirements to the network, allowing packetization, transport, and wireless scheduling decisions to directly improve what users see and how quickly they can interact.

### Progressive loading for networked VR

Conventional VR streaming treats a large application object, such as an octree node, as the smallest decodable unit even though the network divides it across many packets. A lost packet can therefore block useful data that has already arrived and delay visual updates.

I designed packet-aligned encoding and rendering mechanisms that make each received network packet immediately usable for progressive visual refinement. I also evaluated transport strategies for mitigating head-of-line blocking, including SCTP unordered delivery and multiple concurrent QUIC streams. A Unity prototype tested with static and dynamic point clouds under synthetic networks and real network traces showed smoother frame updates and fewer stalls.

This work appeared at **ACM Multimedia 2025** as *RUN: A Case for Cross-Layer Networked Virtual Reality*.

### Scalable collocated multi-user VR

When many collocated users explore the same virtual environment, conventional unicast repeatedly sends overlapping scene content over the same Wi-Fi channel. I developed an application-layer multicast system that exploits spatial coherence among users while remaining deployable on commodity routers and VR headsets.

The system partitions the environment into independently decodable fixed-size packets, prioritizes packets using precomputed visibility, and uses compact bitmap acknowledgments to provide reliability without per-packet feedback. Its transmission and feedback costs remain independent of group size. A controlled study with 23 participants, in groups of 7 and 16, showed substantially faster scene reconstruction and fewer missing regions than conventional TCP unicast.

This work appeared in **IEEE Transactions on Visualization and Computer Graphics** and at **IEEE VR 2026** as *Scalable Collocated Multi-User VR Through Virtual Environment User Spatial Coherence*.

### Adaptive redundancy scheduling for multi-user VR

Multicast removes duplicate transmissions, but packet loss and heterogeneous receiver conditions make fixed retransmission or redundancy policies inefficient. I designed layered packetization for 3D Gaussian Splatting scenes and a belief-driven scheduler that decides when to send new data, retransmissions, or Random Linear Network Coding redundancy.

The scheduler estimates each receiver's reception state and weights recovery decisions by the visual importance of missing content from that user's viewpoint. Trace-driven experiments and tests on Meta Quest 3 headsets show that perception-aware adaptive redundancy improves progressive visual quality over policies with no redundancy or non-adaptive redundancy.

### Real-time VR traffic scheduling

My ongoing work extends the thesis from progressive scene loading to latency-sensitive synchronization, state, and interaction traffic. I formulated an end-to-end, slack-aware scheduling framework that combines receiver-specific latency budgets derived from application semantics with observed uplink delays. The framework is being evaluated through ns-3 simulations and an OpenWrt testbed.

## QoE-based routing path selection

**Purdue University and Juniper Networks · 2022–2023**

I studied why equal-cost multipath routing and average-load policies can degrade video quality when paths carry traffic with similar mean rates but different burstiness. The project connects passive network measurements to the quality experienced by adaptive-streaming and real-time-conferencing users.

- Characterized seven conferencing services, five streaming services, and seven WIDE backbone traces using dispersion, kurtosis, skewness, and prominence at multiple aggregation time scales.
- Designed a lightweight path-load estimator, inspired by TCP retransmission-timeout computation, that combines exponentially smoothed bandwidth with its deviation to steer new long-lived flows away from bursty paths.
- Built a Mininet testbed on CloudLab with DASH and WebRTC workloads, on/off background traffic, and application-level QoE measurements including rebuffering, quality variation, VMAF, PSNR, and SSIM.
- Improved streaming QoE by **14% on average** and reduced conferencing packet latency by **11%** in the preliminary evaluation, while also improving link utilization in undersubscribed scenarios.

This work appeared at **IEEE HPSR 2023** as *Toward QoE-based Routing Path Selection*.

## Scheduling diverse QUIC streams

**Purdue University · 2022**

Extended `quiche` to study sender-side scheduling across reliable QUIC streams and unreliable datagrams. Implemented static, dynamic-priority, and weighted round-robin schedulers and evaluated CPU, memory, and queueing-delay tradeoffs.

## Multi-domain optical network testbed

**University of California, Davis · 2020**

Developed a deep-reinforcement-learning system for routing, modulation, and spectrum assignment in hierarchical multi-domain elastic optical networks. Integrated DRL agents with the ONOS SDN controller and achieved lower connection-blocking probability than a k-shortest-path baseline.

## RDMA optimization for MongoDB

**University of Science and Technology of China · 2018**

Replaced TCP/IP-based MongoDB cluster data transfer with RDMA to reduce communication latency, achieving up to **3.58× Put** and **6.16× Get** peak-throughput improvement over the TCP/IP baseline.
