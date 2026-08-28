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

I develop cross-layer scheduling frameworks for VR streaming over Wi-Fi. The goal is to deliver the content that matters most to a user while working within bandwidth, latency, and packet-loss constraints.

- Designed packet-level progressive streaming for static 3D/VR data so partial scenes can be decoded and rendered before a full download completes.
- Evaluated QUIC and SCTP delivery policies, including stream prioritization and out-of-order delivery.
- Developed adaptive policies that balance new data, retransmissions, and random linear network coding redundancy for multi-user VR.
- Explored joint scheduling of static assets and delay-sensitive synchronization, consistency, and interaction updates.

## QoE-based routing path selection

**Purdue University and Juniper Networks · 2022–2023**

Investigated path-selection strategies driven by application-level quality of experience instead of relying only on conventional network-layer metrics. The work studied how network control can respond to the performance that applications and users actually observe.

## Scheduling diverse QUIC streams

**Purdue University · 2022**

Extended `quiche` to study sender-side scheduling across reliable QUIC streams and unreliable datagrams. Implemented static, dynamic-priority, and weighted round-robin schedulers and evaluated CPU, memory, and queueing-delay tradeoffs.

## Multi-domain optical network testbed

**University of California, Davis · 2020**

Developed a deep-reinforcement-learning system for routing, modulation, and spectrum assignment in hierarchical multi-domain elastic optical networks. Integrated DRL agents with the ONOS SDN controller and achieved lower connection-blocking probability than a k-shortest-path baseline.

## RDMA optimization for MongoDB

**University of Science and Technology of China · 2018**

Replaced TCP/IP-based MongoDB cluster data transfer with RDMA to reduce communication latency, achieving up to **3.58× Put** and **6.16× Get** peak-throughput improvement over the TCP/IP baseline.
