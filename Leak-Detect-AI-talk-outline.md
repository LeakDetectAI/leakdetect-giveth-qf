### Devcon 8 Workshop Discussion

### The Trillion-Dollar Attack Surface: Cross-Layer Security for DeFi

### Summary

DeFi security has traditionally focused on what can **break**: smart-contract exploits, compromised keys, phishing, malicious transactions, and protocol-level vulnerabilities.

But decentralized systems face another class of security risk: **what they unintentionally reveal**.

Modern Ethereum applications increasingly span:

**Users → Autonomous Agents → Dapps → Wallets → Ethereum → P2P Infrastructure**

At every layer, systems generate observable signals—transaction timing, gas usage, signing behavior, API interactions, RPC patterns, network propagation, peer relationships, and on-chain activity. Individually, these signals may appear harmless. When correlated, they can reveal user intent, trading strategies, internal state, or other sensitive information without exploiting a conventional software vulnerability.

This workshop introduces **cross-layer leakage analysis** as a new methodology for Ethereum and DeFi security.

The core thesis is:

> **Ethereum is vulnerable not only to what breaks, but also to what it unintentionally reveals.**

The workshop will combine existing side-channel and leakage-analysis research with Ethereum-native security challenges, including wallets, autonomous agents, multi-chain applications, DeFi protocols, and P2P infrastructure.

---

### The Problem No One Is Watching

Ethereum security today focuses heavily on visible threats: smart-contract vulnerabilities, compromised private keys, phishing, malicious approvals, oracle manipulation, MEV, and protocol exploits.

These remain critical.

However, there is a less visible class of attacks where the underlying system can behave correctly while still leaking information.

Potential signals include:

* Transaction timing
* Gas consumption patterns
* Signing behavior
* RPC and API activity
* Transaction construction
* Agent decision patterns
* Dapp interaction sequences
* Network propagation
* Peer and connection behavior
* Cross-chain execution
* On-chain activity

An adversary can potentially correlate these observations to infer information that the system never explicitly intended to expose.

This can create risks including:

* User or agent identification
* Intent inference
* Strategy prediction
* Internal-state reconstruction
* Privacy loss
* Deanonymization
* Transaction manipulation
* MEV opportunities
* Cross-layer correlation attacks
* Potential key or secret inference in vulnerable implementations

Importantly, these attacks do not necessarily require a smart-contract bug, compromised private key, or broken cryptographic primitive.

They exploit **information leakage created by system behavior**.

This class of attack builds on decades of research in side-channel analysis, cryptographic leakage detection, and adversarial inference, including practical demonstrations such as TLS padding-oracle attacks and other timing- and behavior-based attacks.

The challenge is bringing these techniques into the Ethereum ecosystem and applying them to the systems now being built around autonomous agents, wallets, DeFi, and multi-chain infrastructure.

---

### From "Security Under Execution" to "Security Under Observation"

Traditional security asks:

> **Is this system safe to execute?**

We propose adding another question:

> **Is this system safe to observe?**

A protocol can execute correctly while leaking enough information through timing, behavior, metadata, or correlations to become exploitable.

This leads to a broader security model:

**Correctness + Confidentiality + Privacy + Observability Resistance**

The workshop will explore how we can begin measuring this property systematically.

---

### What Is LeakDetect?

**LeakDetect** is an open-source research framework for detecting, measuring, and simulating hidden information leakage in Ethereum wallets, AI agents, and multi-chain systems.

The framework is designed to enable developers and researchers to:

* Simulate realistic adversaries observing a system
* Capture execution and behavioral signals
* Analyze timing, gas, API, and transaction patterns
* Apply machine learning to infer potentially sensitive information
* Quantify information leakage
* Compare different implementations and mitigations
* Build reproducible leakage experiments
* Develop security benchmarks and datasets

The goal is to move from:

**"We think this system might leak information"**

to:

**"We can reproduce, measure, quantify, and mitigate the leakage."**

---

### Research Foundations

LeakDetectAI builds on more than three years of active open-source development conducted through research at the **Research Center Trustworthy Data Science and Security, Ruhr-Universität Bochum**, together with more than five years of foundational research in AI, cryptography, and security at the **Software Innovation Campus Paderborn (SICP)**.

The research is led by **Dr. Pritha Gupta** and is now being translated into Ethereum-native security tooling and ecosystem applications.

Existing research and open-source work includes:

* [deep-learning-sca](https://github.com/LeakDetectAI/deep-learning-sca)
* [AutoMLQuantILDetect](https://github.com/LeakDetectAI/AutoMLQuantILDetect)
* [automl-qild-experiments](https://github.com/LeakDetectAI/automl-qild-experiments)
* [AutoSCA Hardware Wallet Tester](https://github.com/LeakDetectAI/autosca-hw-wallet-tester)

These projects demonstrate work in:

* AI-driven side-channel analysis
* Automated vulnerability detection
* Neural Architecture Search
* Automated attack optimization
* Large-scale experimental pipelines
* Hardware-wallet security testing
* Information-leakage quantification

Additional research, demonstrations, and publications are available through:

* [LeakDetectAI research resources](https://tinyurl.com/leakdetectai)
* [Sovra Labs](https://sites.google.com/view/sovralabs)

---

### Real-World Foundations

The approach is aligned with existing deployed security research such as **AutoSCA**, an automated side-channel analysis tool:

* [AutoSCA GitHub repository](https://github.com/achelos/AutoSCA)
* [achelos](https://www.achelos.de/en/)
* [AutoSCA demonstration](https://www.youtube.com/watch?v=-ljLPgrw-DY&t=388s)

AutoSCA demonstrates the feasibility of automatically detecting side-channel vulnerabilities using machine learning, including research around TLS and Bleichenbacher-style vulnerabilities.

LeakDetect extends this direction into:

**Ethereum + Wallets + Autonomous Agents + DeFi + Multi-chain Systems + P2P Infrastructure**

The goal is not to reproduce existing cryptographic side-channel research, but to apply its methodology to the increasingly complex information flows created by decentralized systems.

---

### Why This Matters Now

Ethereum is rapidly changing.

AI agents are beginning to:

* Hold assets
* Sign transactions
* Interact with dapps
* Manage liquidity
* Execute strategies
* Coordinate across chains
* Make decisions without continuous human intervention

At the same time, applications are becoming increasingly multi-chain and composable.

This creates a much larger observable surface.

An autonomous agent may reveal information through its decision timing.

A wallet may reveal information through simulation and RPC interactions.

A dapp may reveal information through request patterns.

Ethereum may reveal information through transaction behavior.

The P2P network may reveal information through propagation and connection patterns.

The attacker can potentially correlate all of these.

This means the security boundary is no longer simply the smart contract.

---

### The Cross-Layer Security Model

The workshop will introduce the following conceptual model:

```text
                    ┌──────────────────────┐
                    │        USER          │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │   AUTONOMOUS AGENT   │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │        DAPP          │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │       WALLET         │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │      ETHEREUM         │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │    P2P / NETWORK      │
                    └──────────────────────┘
```

At each layer we ask:

**What can be observed?**

Then:

**What can be inferred?**

Then:

**What can be correlated across layers?**

Finally:

**Can that inference create a security, privacy, or economic advantage?**

---

### Seven Security Questions

The workshop will focus on seven questions.

### 1. What does the system expose?

What signals are observable during normal execution?

### 2. What can an attacker infer?

Can observations reveal intent, identity, strategy, state, or secrets?

### 3. Can observations be correlated?

Can information from wallets, dapps, agents, Ethereum, and the network be combined?

### 4. Can behavior be predicted?

Can an attacker predict what a user, agent, or protocol will do next?

### 5. Can the behavior be attributed?

Can activity be linked back to a specific user, wallet, agent, or node?

### 6. Can inference become exploitation?

Does the information provide an economic, privacy, or security advantage?

### 7. Can we mitigate the leakage?

Can the system reduce leakage without sacrificing usability, decentralization, or performance?

---

### Workshop Structure

The workshop will be designed as a combination of a short technical introduction, threat-modeling exercise, practical analysis, and discussion.

### Part 1 — The Invisible Attack Surface

We introduce the difference between conventional vulnerability exploitation and leakage-based attacks.

Participants examine examples where systems behave correctly but unintentionally reveal information.

### Part 2 — Mapping the DeFi Transaction

Participants start with a representative transaction:

**User → Agent → Dapp → Wallet → RPC → Ethereum → P2P → Blockchain**

They identify what information becomes observable at each stage.

### Part 3 — Cross-Layer Correlation

Participants then examine how observations from multiple layers can be combined.

For example:

**Agent timing + Wallet simulation + RPC activity + Transaction propagation + On-chain execution**

The objective is to determine whether the combined signals reveal more than any individual observation.

### Part 4 — Threat Modeling

Participants classify potential leakage according to:

* Identification
* Inference
* Attribution
* Prediction
* Confidentiality
* Privacy
* Economic exploitation

### Part 5 — Measurement

We introduce the principles behind reproducible leakage experiments.

The basic workflow is:

**Observation → Correlation → Inference → Exploitation → Measurement → Mitigation**

### Part 6 — Mitigation

Participants consider mitigations at different layers:

* Application architecture
* Wallet design
* Agent design
* RPC infrastructure
* Transaction handling
* Privacy mechanisms
* P2P protocols
* Network architecture

---

### What Participants Will Take Away

Participants will leave with a practical methodology for identifying security and privacy leakage outside the traditional smart-contract boundary.

They will understand how seemingly weak signals can become powerful when correlated and how to construct cross-layer threat models for DeFi protocols, wallets, and autonomous agents.

Participants will also learn how to design reproducible experiments that measure leakage rather than relying solely on qualitative security assumptions.

The intended progression is:

> **Observe → Correlate → Infer → Exploit → Quantify → Mitigate**

This methodology can be applied to existing DeFi systems as well as emerging agentic and multi-chain architectures.

---

### Security, Privacy and CROPS Alignment

The workshop directly supports Devcon's focus on **Censorship Resistance, Open Source, Privacy, and Security (CROPS)**.

### Security

The central objective is to identify previously under-measured attack surfaces and develop methods to detect and mitigate exploitable information leakage.

### Privacy

Cross-layer correlation can expose information about users, transaction intent, strategies, identities, and behavioral patterns even when explicit private information is never transmitted.

### Open Source

LeakDetect is built around open-source research, public repositories, reproducible experiments, datasets, benchmarks, and ecosystem collaboration.

### Censorship Resistance

Understanding network-level metadata and P2P behavior is important for evaluating whether decentralized communication can reveal information that enables targeted disruption, selective observation, or other forms of network-level interference.

The workshop therefore treats CROPS not as isolated properties, but as interconnected security requirements of decentralized systems.

---

### From Individual Components to System Security

One of the central conclusions of the workshop is:

> **Individually secure components do not necessarily produce a secure system.**

A wallet can be secure.

A dapp can be secure.

A smart contract can be secure.

A P2P protocol can be secure.

An AI agent can be secure.

Yet the complete system can still leak sensitive information through the interactions between those components.

This is why cross-layer analysis is necessary.

The attacker does not have to attack the strongest component.

They can exploit the **connections between components**.

---

### Current Research Progress

The underlying research has already demonstrated:

* Large-scale leakage detection experiments using deep learning
* Automated vulnerability-discovery pipelines
* AutoML and Neural Architecture Search for leakage analysis
* Real-world adversarial inference simulations
* Benchmarks across GPU clusters and consumer hardware
* Security analysis of multi-chain deployments
* ERC-20 ecosystem analysis across 13+ chains
* Automated hardware-wallet security testing

The next stage is to bring these capabilities into Ethereum-native workflows and make them accessible to developers, researchers, auditors, wallet teams, and protocol security engineers.

---

### What We Aim to Build

The broader research roadmap includes five areas.

### 1. Production-Ready Open-Source Toolkit

A CLI and SDK for leakage testing, with integrations for wallets, agents, and decentralized applications.

### 2. Public Benchmarks and Datasets

Standardized datasets and reproducible environments for comparing leakage across implementations, chains, wallets, and applications.

### 3. Ecosystem Integrations

Integrations with:

* Wallet providers
* AI agent frameworks
* Multi-chain dapps
* DeFi protocols
* Ethereum infrastructure
* P2P systems

### 4. Security Metrics

We are exploring standardized metrics including:

* **Vulnerability Score (VS)**
* **Key Recovery Probability (KRP)**
* **Information Leakage Rate (ILR)**
* **Stealth Leakage Index (SLI)**

These metrics aim to turn information leakage into something that can be measured, compared, tracked, and eventually incorporated into security assessments.

### 5. Community and Education

Open documentation, workshops, tutorials, security benchmarks, and educational material designed to make leakage-based security accessible to the broader Ethereum ecosystem.

---

### Public Goods and Open Source

Hidden leakage is fundamentally a public-goods problem.

A leakage vulnerability in a wallet, protocol, agent framework, or infrastructure component can potentially affect thousands or millions of users.

The incentives to discover these vulnerabilities proactively are therefore not limited to the original developer.

The broader ecosystem benefits from:

* Open research
* Public datasets
* Reproducible experiments
* Shared benchmarks
* Open-source detection tools
* Community security education

LeakDetect is intended to contribute these resources back to the Ethereum ecosystem.

---

### Community Support and Ecosystem Alignment

The research has received ecosystem support through contributions and funding from the **Ethereum Foundation's DAO Fund, Giveth, Wintermute, and the Trillion Security Research initiative**.

The Giveth project is available here:

[LeakDetect: Protecting Ethereum from Hidden Leakages](https://giveth.io/project/leak-detect:-protecting-ethereum-from-hidden-leakages)

The initiative is specifically focused on identifying what decentralized systems unintentionally reveal and developing practical, reproducible techniques to detect and mitigate those risks.

---

# Broader Vision

The long-term goal is to change how we think about decentralized-system security.

Today we often ask:

> **"Is this system safe to run?"**

We should increasingly also ask:

> **"Is this system safe to observe?"**

Because in decentralized systems, observation itself can become an attack primitive.

The trillion-dollar security challenge is therefore not only protecting what Ethereum stores or executes.

It is understanding **what the entire system reveals while doing so**.

---

# Discussion Questions

We would particularly welcome feedback from Devcon contributors and researchers on the following questions:

1. **What forms of cross-layer leakage should Ethereum security researchers prioritize?**

2. **How should leakage resistance be incorporated into wallet and DeFi security assessments?**

3. **What signals should be included in a common Ethereum leakage benchmark?**

4. **How can we measure the economic impact of information leakage?**

5. **What leakage risks will become more important as autonomous agents begin managing significant amounts of capital?**

6. **How should P2P/network-level metadata be incorporated into DeFi threat models?**

7. **What should an open standard for decentralized-system leakage metrics look like?**

8. **Which wallets, dapps, protocols, agent frameworks, and infrastructure projects would be good candidates for initial collaborative testing?**

---

# Open Source Repositories

* [LeakDetectAI](https://github.com/LeakDetectAI)
* [Deep Learning Side-Channel Analysis](https://github.com/LeakDetectAI/deep-learning-sca)
* [AutoMLQuantILDetect](https://github.com/LeakDetectAI/AutoMLQuantILDetect)
* [AutoML QILD Experiments](https://github.com/LeakDetectAI/automl-qild-experiments)
* [AutoSCA Hardware Wallet Tester](https://github.com/LeakDetectAI/autosca-hw-wallet-tester)
* [AutoSCA](https://github.com/achelos/AutoSCA)

---

### Research & Background

* [LeakDetectAI Research Resources](https://tinyurl.com/leakdetectai)
* [Sovra Labs](https://sites.google.com/view/sovralabs)
* [Giveth — LeakDetect: Protecting Ethereum from Hidden Leakages](https://giveth.io/project/leak-detect:-protecting-ethereum-from-hidden-leakages)

---

### Call for Discussion

We are proposing **The Trillion-Dollar Attack Surface: Cross-Layer Security for DeFi** as a hands-on Devcon workshop.

The goal is not simply to present another security checklist. It is to establish a common vocabulary and practical methodology for a security problem that sits between existing disciplines: **side-channel analysis, DeFi security, wallet security, AI-agent security, privacy, Ethereum protocol security, and P2P networking.**

We would welcome feedback from the Devcon community on the threat model, workshop exercises, candidate datasets, metrics, and potential ecosystem integrations.

**The central question for the workshop is simple:**

> ### What is Ethereum unintentionally revealing—and can we measure it before someone learns how to exploit it?
