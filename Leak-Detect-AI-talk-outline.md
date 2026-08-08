## Talk / Workshop Details

### The Trillion-Dollar Attack Surface: Cross-Layer Security for DeFi

DeFi security has traditionally focused on smart contracts, wallets, and transaction-level vulnerabilities. However, modern decentralized applications increasingly operate across a much broader stack: **users → autonomous agents → dapps → wallets → Ethereum → P2P infrastructure**.

This talk/workshop explores a fundamental question:

> **What can decentralized systems unintentionally reveal when seemingly harmless signals from different layers are combined?**

An attacker may not need to compromise a private key or exploit a smart contract. By correlating transaction timing, wallet behavior, dapp interactions, agent decisions, RPC activity, network propagation, and on-chain data, an adversary may be able to infer sensitive information or gain an economic advantage.

The session introduces **cross-layer leakage analysis** as a security methodology for DeFi and decentralized systems.

### Key Points

**1. Moving beyond smart-contract-centric security**

We will examine why conventional audits and threat models can miss vulnerabilities that emerge between layers, particularly where application, wallet, transaction, privacy, and network behavior intersect.

**2. Autonomous agents introduce a new attack surface**

As agents increasingly make financial decisions and execute transactions autonomously, their observations, timing, decisions, retries, and communication patterns can reveal information about their strategies and user intent.

**3. Wallets are becoming decision boundaries**

Modern wallets do much more than hold keys. Transaction simulation, policy enforcement, RPC selection, dapp interaction and agentic functionality can all influence what users ultimately sign and broadcast.

**4. P2P metadata can become financial security data**

Transaction propagation, timing, peer relationships, connection patterns and other network-level signals can potentially be correlated with on-chain activity. Network privacy therefore becomes relevant to DeFi security and MEV.

**5. Cross-layer correlation is the key problem**

A single observation may appear harmless. Combining observations across agents, dapps, wallets, Ethereum and P2P infrastructure can reveal substantially more. We will introduce a framework for studying this correlation systematically.

**6. From anecdotes to measurable security**

The goal is to make leakage measurable and reproducible. We will discuss datasets, controlled experiments, adversarial evaluation, correlation analysis and metrics for identification, inference, attribution, prediction and potential economic exploitation.

**7. From research to practical mitigations**

The objective is not simply to identify vulnerabilities. The research will explore practical mitigations at the application, wallet, agent, RPC, protocol and networking layers while preserving usability, decentralization and performance.

### Workshop Objectives

By the end of the session, participants should be able to:

* Identify security and privacy leakage outside the traditional smart-contract boundary.
* Map information flows across users, agents, dapps, wallets, Ethereum and P2P infrastructure.
* Recognize how individually weak signals can become powerful when correlated.
* Develop cross-layer threat models for DeFi applications and autonomous agents.
* Understand how network-level metadata can affect financial security.
* Design reproducible experiments for measuring information leakage.
* Identify potential mitigations and areas for further research.

### Practical Component

If delivered as a workshop, participants will work through a representative DeFi transaction flow and construct a **cross-layer leakage map**.

We will examine what an adversary could potentially observe at each stage, what information could be inferred by correlating those observations, and whether the resulting inference could create a security, privacy or economic risk.

The exercise will move from:

**Observation → Correlation → Inference → Exploitation → Mitigation**

This provides participants with a practical methodology they can apply to their own protocols, wallets, dapps and agentic systems.

### Broader Research Initiative

The session is part of a broader research effort focused on identifying what decentralized systems unintentionally reveal and developing practical, reproducible methods to detect and mitigate leakage before it becomes a security or privacy problem.

The work brings together research across **Ethereum, DeFi, wallet security, privacy, autonomous agents, decentralized storage and P2P/libp2p infrastructure**, with an emphasis on open research, reproducible datasets and community collaboration.

The initiative is supported through contributions and funding from the **Ethereum Foundation's DAO Fund, Giveth, Wintermute and the Trillion Security Research initiative**.

### Intended Audience

The session is designed for:

* DeFi and protocol security researchers
* Smart-contract auditors
* Wallet and infrastructure developers
* MEV researchers
* Privacy researchers
* AI/agent security researchers
* Ethereum and P2P protocol developers
* Developers building autonomous financial agents

No specialized knowledge of P2P networking or privacy research is required. The session will begin with familiar DeFi security concepts and progressively expand the threat model to the broader decentralized systems stack.
