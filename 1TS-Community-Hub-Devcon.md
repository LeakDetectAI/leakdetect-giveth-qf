# Leak Detect AI — Cross-Layer Ethereum Security & Resilient Communication Hub

### Please give a short description of the topic/cause for your Community Hub

**Leak Detect AI** is a community-led security research and education initiative focused on understanding and measuring security, privacy, and communication risks across the Ethereum stack—from wallets, dApps, agents and tooling to Ethereum's underlying P2P networking infrastructure.

The hub will provide a practical environment where Ethereum developers, security researchers, protocol engineers, students, and community members can investigate real-world security datasets, model cross-layer attacks, and explore defensive infrastructure. Activities will include analysis of public Zcash and Tornado Cash datasets from a privacy and metadata-leakage perspective; secure communication between wallets, agents and developer tooling; P2P threats such as Sybil, eclipse and network-partition attacks; and post-quantum approaches to libp2p and Ethereum light-client communication.

Leak Detect AI is supported through the **EF DAO Fund via Giveth**, has been invited to the **1 Trillion Security initiative of Ethereum**, and is supported by **Wintermute**, with advice and technical input from members of the libp2p, IPFS and Filecoin communities.

---

# What will you offer to the Devcon attendees?

We will offer Devcon attendees a **four-day, community-led security research and hands-on engineering hub** focused on understanding Ethereum as an end-to-end security and communication system.

Rather than treating smart contracts, wallets, agents and P2P networks as isolated layers, the hub will demonstrate how information can leak or attacks can propagate across these layers—and how measurement, secure communication protocols and resilient infrastructure can reduce these risks.

Participants will be able to:

* Build threat models for Ethereum users, wallets, agents, dApps and infrastructure.
* Work with **public Zcash and Tornado Cash datasets** to investigate privacy, metadata leakage, transaction-graph patterns and the limits of defensive analysis.
* Explore how wallets, agents, RPC providers and developer tooling communicate, and identify weaknesses in communication channels.
* Understand how **P2P-layer attacks—including Sybil, eclipse and network-partition attacks—can affect higher-level Ethereum applications and users**.
* Experiment with **Luminar** as a measurement and observability layer for identifying and mitigating P2P attacks.
* Explore post-quantum signatures and their integration into **libp2p specifications using PKIX-compatible approaches**.
* Discuss interoperability of post-quantum authenticated communication with **Ethereum L1 and L2 networks**.
* Rethink the design of Ethereum P2P communication from the perspective of **post-quantum light clients**.
* Connect researchers and developers from the Ethereum, libp2p, IPFS, Filecoin and broader decentralized-systems communities.

The hub will combine **short technical talks, live demonstrations, threat-modelling exercises, dataset analysis, protocol experiments and open community discussions**. All exercises will be designed around defensive security, responsible research and reproducible measurement.

---

# Rough Program Outline

The hub will run across **all four days of Devcon**, with each day focused on a different layer of the Ethereum security stack. **Leak Detect AI will be the continuous research and measurement thread across all four days**, connecting the individual sessions into one broader investigation of Ethereum's attack surface.

---

## Day 1 — Leak Detect AI, Privacy Leakage & Cross-Layer Threat Modeling

The first day introduces Leak Detect AI and establishes a common security framework for thinking about Ethereum beyond smart contracts.

### Topics

* Introduction to Leak Detect AI and the cross-layer security problem.
* From smart-contract security to **user → wallet → dApp → agent → RPC → Ethereum → P2P network**.
* Threat modelling for Ethereum users and infrastructure.
* Information leakage versus direct compromise.
* Metadata leakage, transaction timing, network observations and correlation risks.
* Privacy-preserving analysis of publicly available blockchain datasets.
* Working with **Zcash and Tornado Cash datasets**.
* What transaction graphs can and cannot reveal.
* Understanding the difference between legitimate security research, privacy analysis and deanonymization.
* Identifying cross-layer signals that could expose users, agents or infrastructure.
* Building reproducible datasets and measurement methodologies for security research.

### Hands-on session

Participants will work in small groups with prepared datasets and threat models to identify:

**What information is visible at each layer?**

```text
User
  ↓
Wallet
  ↓
dApp / Agent
  ↓
RPC / API
  ↓
Ethereum L1 / L2
  ↓
libp2p / P2P Network
  ↓
Peers / Relays / Observers
```

The exercise will use Leak Detect AI to map potential leakage paths and distinguish between application-level, protocol-level and network-level observations.

### Day 1 outcome

Participants leave with a practical understanding of **cross-layer security and privacy leakage**, plus a threat model that will be used during the remaining three days.

---

# Day 2 — Secure Communication for Ethereum Wallets, Agents & Tooling

Day 2 moves from privacy analysis to the **communication infrastructure connecting Ethereum applications and users**.

The central question will be:

> **Can we trust the communication channels through which wallets, agents, dApps and developer tools exchange security-sensitive information?**

### Topics

* Secure communication architecture for Ethereum wallets.
* Wallet ↔ dApp communication.
* Wallet ↔ RPC communication.
* Agent ↔ wallet communication.
* Agent ↔ agent communication.
* Agent ↔ tool/API communication.
* Secure discovery and authentication.
* Identity, authorization and capability boundaries.
* Message integrity and authenticity.
* Replay and downgrade risks.
* Metadata leakage through communication channels.
* Compromised front ends and malicious infrastructure.
* Secure communication for autonomous agents.
* How P2P communication differs from centralized RPC architectures.
* Where libp2p, IPFS and decentralized networking primitives can strengthen Ethereum tooling.

### Hands-on exercises

Participants will model several communication scenarios:

1. **Wallet → dApp**
2. **Wallet → RPC**
3. **Agent → Wallet**
4. **Agent → Agent**
5. **Agent → P2P Network**
6. **Ethereum application → decentralized storage/network infrastructure**

Leak Detect AI will be used to identify possible observable signals and leakage points.

The session will also explore how secure communication protocols can be designed so that **authentication, privacy and availability are preserved even when individual infrastructure components are compromised**.

### Day 2 outcome

Participants will produce communication threat models and identify concrete requirements for **secure, authenticated and privacy-preserving communication channels** for Ethereum wallets, agents and tooling.

---

# Day 3 — P2P Resilience: Sybil, Eclipse, Network Partition & Luminar

Day 3 focuses on the security layer that is often invisible to application developers: **Ethereum's underlying P2P networking infrastructure**.

### Topics

* Why P2P security is application security.
* libp2p threat models.
* Sybil attacks.
* Eclipse attacks.
* Network partition attacks.
* Peer discovery manipulation.
* Routing and topology attacks.
* Connection diversity and peer selection.
* GossipSub security considerations.
* Network observability and measurement.
* Detecting abnormal peer behaviour.
* Measuring connectivity and resilience.
* Using **Luminar** for security measurement and attack detection.
* Connecting P2P observations to higher-level Ethereum security events.

### Luminar workshop

A major practical component will be a hands-on exploration of **scaling Luminar as a measurement and detection layer for decentralized networks**.

Participants will explore:

* How to collect network-level measurements.
* How to identify anomalous peer behaviour.
* Detecting potential Sybil clusters.
* Detecting eclipse-like connectivity patterns.
* Identifying network partitions.
* Measuring peer diversity and connectivity.
* Correlating network observations with application-level events.
* Designing reproducible P2P security experiments.
* Building dashboards and measurements that can be used by protocol developers.

The objective is not simply to demonstrate attacks, but to ask:

> **How can we continuously measure whether a decentralized network is becoming more or less resilient?**

### Day 3 outcome

Participants will understand how P2P failures and attacks can propagate upward into Ethereum applications, and will experiment with **measurement-driven approaches to detecting and mitigating Sybil, eclipse and network-partition risks**.

---

# Day 4 — Post-Quantum Ethereum: libp2p, L1/L2 Interoperability & PQ Light Clients

The final day looks beyond today's security model and asks how Ethereum's networking layer should evolve for a **post-quantum future**.

### Topics

* Why post-quantum security matters for Ethereum networking.
* Limitations of existing public-key assumptions.
* Post-quantum signatures and authenticated communication.
* Integrating quantum-resistant signatures into libp2p.
* **PKIX-compatible approaches to post-quantum identity and authentication.**
* Key exchange versus signatures.
* Migration and algorithm agility.
* Backward compatibility with existing libp2p deployments.
* Interoperability with Ethereum L1 and L2 environments.
* PQ-secure wallet and agent communication.
* Post-quantum networking for decentralized applications.
* Long-lived identities and cryptographic migration.

### PQ Light Client discussion

The day will culminate in a research discussion around:

> **Should we simply replace existing cryptography in Ethereum light clients, or should we rethink the P2P trust and communication model itself for a post-quantum world?**

Discussion topics will include:

* Post-quantum light-client architectures.
* Alternative committee and trust models.
* Reducing dependence on individual cryptographic assumptions.
* P2P requirements for lightweight clients.
* Network-level verification.
* Synchronization and authenticated data dissemination.
* Trade-offs between bandwidth, computation, latency and security.
* How PQ light clients could interact with Ethereum L1 and L2.
* Implications for libp2p and future Ethereum networking standards.

### Final collaborative session

The final session will bring together the four days:

**Privacy → Communication → P2P Resilience → Post-Quantum Security**

Participants will map how these layers interact and identify research and engineering questions that could be pursued after Devcon.

### Day 4 outcome

A community discussion and working roadmap for **post-quantum-ready Ethereum communication infrastructure**, including potential directions for libp2p specifications, Ethereum interoperability and PQ light clients.

---

# Four-Day Theme at a Glance

| Day       | Theme                                 | Leak Detect AI Focus                                            | Practical Output               |
| --------- | ------------------------------------- | --------------------------------------------------------------- | ------------------------------ |
| **Day 1** | Privacy & Cross-Layer Threat Modeling | Zcash/Tornado Cash datasets, metadata leakage, threat modelling | Cross-layer threat models      |
| **Day 2** | Secure Wallet & Agent Communication   | Communication-channel leakage and authentication                | Secure communication models    |
| **Day 3** | P2P Resilience                        | Luminar, Sybil, eclipse & partition detection                   | P2P measurement experiments    |
| **Day 4** | Post-Quantum Ethereum                 | PQ signatures, PKIX, L1/L2 & PQ light clients                   | PQ networking research roadmap |

---

# People who will organise, oversee and be responsible for the Community Hub

I would keep this section role-based unless the Devcon application specifically requires confirmed individual names:

* **Leak Detect AI Core Team** — Overall hub leadership, research direction and security methodology
* **Leak Detect AI Security Researchers** — Dataset analysis, threat modelling and cross-layer leakage research
* **libp2p Community Contributors** — P2P security, networking, protocol design and interoperability
* **IPFS / Filecoin Community Contributors** — Decentralized networking, storage and infrastructure security
* **Ethereum Security Researchers & Builders** — Ethereum L1/L2, wallets, agents and application-layer security
* **P2P Networking / Luminar Contributors** — Network measurement, observability and resilience experiments
* **Community Facilitators** — Workshops, participant support and documentation
* **Devcon Community Hub Coordinator** — Daily scheduling, logistics and coordination with Devcon

### Supporting ecosystem

Leak Detect AI is supported by the **EF DAO Fund through Giveth**, has been invited to the **1 Trillion Security initiative**, and is supported by **Wintermute**. The initiative also benefits from technical advice and community participation from contributors and maintainers across **libp2p, IPFS and Filecoin**.

---

# Equipment / Production Needs

### Core equipment

* LED TV / large display with HDMI connection for live demonstrations
* Projector or large screen where available
* 2–3 whiteboards for threat modelling and protocol architecture exercises
* Multiple tables for collaborative security research
* Power outlets and extension boards for participant laptops and test devices
* Reliable high-bandwidth Internet connection
* Wi-Fi suitable for simultaneous network experiments
* HDMI/USB-C adapters
* Power strips and charging facilities

### Technical requirements

* Participant laptops
* Local test network / isolated networking environment where possible
* Test Ethereum L1/L2 environments
* libp2p test nodes
* Preconfigured Luminar demonstration environment
* Prepared Zcash and Tornado Cash datasets
* Data-analysis notebooks and reproducible research environments
* Wallets and test accounts for controlled demonstrations
* Test agent environments
* Software for network visualization and threat modelling

### Security / research requirements

Where possible, we would like an **isolated test environment** for P2P experiments so that participants can safely simulate:

* Sybil conditions
* Eclipse scenarios
* Network partitions
* Peer-discovery manipulation
* Communication failures
* Post-quantum authentication experiments

All demonstrations would be conducted against controlled infrastructure rather than attempting to disrupt Devcon or production networks.

---

# Why this Community Hub is valuable to Devcon

A strong final paragraph for the application would be:

> **Leak Detect AI brings together security research that is often fragmented across Ethereum's application, wallet, agent and networking layers.** The hub will give Devcon attendees an opportunity to move beyond purely smart-contract-centric security and examine how privacy leakage, insecure communication, P2P attacks and cryptographic assumptions interact across the complete Ethereum stack. By combining real-world datasets, hands-on threat modelling, network measurement with Luminar, libp2p engineering and post-quantum research, the hub will create a practical environment where researchers and builders can identify vulnerabilities, test defensive approaches and develop ideas that can continue beyond Devcon.

## Suggested title

I would use:

**Leak Detect AI: Securing Ethereum from Wallets to P2P Networks**

with the subtitle:

**A 4-Day Community Hub on Privacy, Secure Communication, Network Resilience & Post-Quantum Ethereum**

This gives Devcon leadership an immediately understandable story while preserving the more ambitious technical work underneath.
