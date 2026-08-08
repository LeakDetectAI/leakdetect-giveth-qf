# DeFi Security Summit 2026 and Devcon 2026 Submission

## Submission Details

**Type of Submission:** Workshop

**Title:**
The Trillion-Dollar Attack Surface: Cross-Layer Security for DeFi

**Abstract (max 250 characters):**
DeFi security extends beyond smart contracts. This workshop explores cross-layer leakage across users, agents, dapps, wallets, Ethereum and P2P networks, and how measurement can reveal and mitigate new attacks. Supported by EF Fund, Giveth & 1TS.

---

## Outline

DeFi security has traditionally focused on smart contracts, wallets, and transaction-level vulnerabilities. However, modern decentralized applications increasingly operate across a much broader stack: users, autonomous agents, dapps, wallets, Ethereum, and the underlying P2P infrastructure. This talk explores how security and privacy risks can emerge across these layers and, importantly, at the boundaries between them.

The central question is: **What can decentralized systems unintentionally reveal when seemingly harmless signals from different layers are combined?** An attacker may not need to compromise a private key or exploit a smart contract. By correlating transaction timing, wallet behavior, dapp interactions, agent decisions, RPC activity, network propagation, and on-chain data, an adversary may be able to infer sensitive information or gain an economic advantage.

The session introduces **cross-layer leakage analysis** as a methodology for DeFi security. We will examine how autonomous agents create new attack surfaces through their decisions, timing, observations, and communication patterns; how wallets are becoming decision boundaries rather than simple key-management tools; and how P2P metadata such as propagation patterns, timing, peer relationships, and connection behavior can become relevant to financial security and privacy.

A key theme is that individually secure components do not necessarily produce a secure system. A single observation may appear harmless, but combining observations across agents, dapps, wallets, Ethereum, and P2P infrastructure can reveal significantly more. The talk will explore how to move from anecdotal concerns about leakage toward measurable and reproducible security analysis using datasets, controlled experiments, adversarial evaluation, and cross-domain correlation.

The research will focus on practical questions around identification, inference, attribution, prediction, and potential economic exploitation. We will also discuss how leakage can be mitigated at multiple layers, including application architecture, wallet design, agent design, RPC infrastructure, privacy mechanisms, and networking protocols, while preserving usability, decentralization, and performance.

If delivered in a workshop format, participants will work through a representative DeFi transaction flow and construct a **cross-layer leakage map**. They will identify what an adversary could observe at each stage, what information could potentially be inferred by correlating those observations, whether the inference creates a security, privacy, or economic risk, and what mitigations could be applied. The methodology follows a practical progression:

**Observation → Correlation → Inference → Exploitation → Mitigation**

The broader objective is to establish a more comprehensive security model for decentralized systems, one that treats information flow across the entire stack as a security property rather than analyzing smart contracts, wallets, agents, privacy, and networking in isolation.

This work is part of a broader research initiative focused on identifying what decentralized systems unintentionally reveal and developing practical, reproducible methods to detect and mitigate leakage before it becomes a security or privacy problem. The research spans Ethereum, DeFi, wallet security, privacy, autonomous agents, decentralized storage, and P2P/libp2p infrastructure, with an emphasis on open research, reproducible datasets, and community collaboration.

The work is supported through contributions and funding from the Ethereum Foundation's DAO Fund, Giveth ([LeakDetect: Protecting Ethereum from Hidden Leakages](https://giveth.io/project/leak-detect:-protecting-ethereum-from-hidden-leakages?utm_source=chatgpt.com)), Wintermute, and the Trillion Security Research initiative ([LeakDetectAI Ethereum 1TS Proposal](https://github.com/LeakDetectAI/leakdetect-giveth-qf/blob/main/LeakDetectAI_Ethereum_1TS_Proposal.md?utm_source=chatgpt.com)).

The session is intended for DeFi and protocol security researchers, smart-contract auditors, wallet and infrastructure developers, MEV and privacy researchers, AI/agent security researchers, and Ethereum/P2P protocol developers.

---

## What will the audience learn from your talk/workshop?

The audience will learn how to think about DeFi security beyond smart contracts and identify security and privacy risks that emerge across the broader decentralized stack: users, autonomous agents, dapps, wallets, Ethereum, and P2P infrastructure.

They will learn how seemingly harmless signals, such as transaction timing, wallet behavior, agent decisions, RPC activity, network propagation, and on-chain data, can be correlated to reveal sensitive information, user intent, trading strategies, or exploitable behavior.

Participants will also learn a practical methodology for **cross-layer leakage analysis**, moving from observation to correlation, inference, exploitation, and mitigation. They will understand how to develop cross-layer threat models, design reproducible leakage experiments, evaluate potential economic impact, and identify mitigations at the application, wallet, agent, privacy, RPC, and networking layers.

Most importantly, the audience will leave with a broader security mindset: **a system can have individually secure components while still exposing exploitable information through the interactions between those components.** This approach can be applied to DeFi protocols, wallets, autonomous agents, and other decentralized systems.

---

## Why is your talk/workshop a good fit for DSS?

This talk is a strong fit for DSS because it addresses an emerging security challenge directly relevant to the future of decentralized finance: **security across the entire transaction and information stack, rather than only within smart contracts.**

As DeFi increasingly incorporates autonomous agents, sophisticated wallets, privacy technologies, MEV infrastructure, cross-chain systems, and decentralized P2P networks, the attack surface is expanding beyond traditional contract-level vulnerabilities. The talk connects these domains and examines how information leaked at one layer can be correlated with observations from another to create security, privacy, or economic risks.

The session also brings a practical and research-oriented perspective. Rather than treating cross-layer leakage as a theoretical privacy concern, we propose measurable threat models, reproducible experiments, adversarial evaluation, and practical mitigations that can be applied by protocol developers, wallet teams, security researchers, and auditors.

This makes the topic particularly relevant to DSS's security-focused audience while also introducing a perspective that is still relatively underrepresented in DeFi security discussions: **the security implications of information flow between users, agents, dapps, wallets, Ethereum, and the underlying network.**

The work is also part of an active research initiative involving Ethereum, DeFi, wallet security, privacy, autonomous agents, and P2P/libp2p infrastructure, with an emphasis on open research and reproducible findings. DSS provides an ideal environment to bring these findings to security practitioners, researchers, and protocol builders and to develop the next generation of cross-layer DeFi security practices.
