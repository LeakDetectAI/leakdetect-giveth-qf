# LeakDetect: Giveth Quadratic Funding Campaign Tracker

## Securing Ethereum Against Hidden Information Leakage

This repository tracks all activities, progress, and deliverables related to the **LeakDetect Ethereum Security Quadratic Funding campaign on Giveth**.

LeakDetect is an open-source security framework designed to **detect and quantify hidden information leakage in Ethereum wallets, AI agents, and decentralized applications**.

While most security tools focus on visible threats, smart contract exploits, phishing, and wallet hacks—LeakDetect addresses a **critical blind spot in blockchain security**: systems that unintentionally leak sensitive information through observable behavior.

This repository provides transparency around the campaign and documents the development of **leakage-aware security tooling for the Ethereum ecosystem**.


# The Problem No One Is Watching

Ethereum security today focuses primarily on **visible vulnerabilities**, such as:

* Smart contract exploits
* Phishing attacks
* Wallet compromises

However, a more subtle and dangerous risk is increasingly being recognized: **information leakage through observable system behavior**.

Even when systems behave correctly, they may leak sensitive information through:

* **Transaction timing**
* **Gas usage patterns**
* **Signing behavior**
* **Cross-chain execution traces**

Adversaries can analyze these signals to infer:

* Private keys
* Internal application logic
* Strategic decisions
* Hidden system states

Importantly, these attacks can occur **without exploiting any bugs**.

As **AI agents begin managing funds and interacting autonomously**, this risk becomes significantly more urgent.

Ethereum isn’t just vulnerable to what breaks.

It’s also vulnerable to **what it unintentionally reveals.**


# What LeakDetect Does

LeakDetect is an **open-source framework** that helps detect and measure hidden information leakage in:

* Ethereum wallets
* AI agents
* decentralized applications
* cross-chain systems

The framework enables developers and researchers to:

• Simulate realistic adversaries observing their systems
• Capture execution signals such as timing, gas, and API patterns
• Apply machine learning models to infer potential secrets
• Quantify risk using measurable security metrics

This introduces a new security paradigm:

**Security under observation, not just correctness under execution.**


# Why This Matters Now

Ethereum is rapidly evolving.

Key trends include:

* AI agents signing transactions
* Autonomous applications managing funds
* Multi-chain deployments across L2 ecosystems
* Cross-chain coordination and automation

However, current security tooling cannot effectively measure **information leakage risks**.

LeakDetect fills this gap by enabling **leakage-aware security testing before vulnerabilities scale across the ecosystem.**


# Our Progress So Far

LeakDetect builds on significant prior research and experimentation.

Our work includes:

• Large-scale experiments on leakage detection using deep learning
• Neural Architecture Search (NAS) pipelines for automated vulnerability discovery
• Simulated adversarial inference attacks
• Benchmarks executed on GPU clusters and consumer hardware

Our experiments demonstrate that:

* Leakage attacks are **feasible today**
* Even **modest compute resources** can exploit these signals
* Sophisticated attackers can **amplify these vulnerabilities significantly**

We also evaluate leakage using widely recognized datasets including:

* ASCAD (fixed & random key variants)
* CHES CTF dataset
* AES_HD / AES_RD datasets
* DPAv4 (DPA contest dataset)


# Related Open Source Work

LeakDetect builds upon several open-source research initiatives.

### LeakDetectAI Organization

[https://github.com/LeakDetectAI](https://github.com/LeakDetectAI)

An open-source research initiative focused on combining **machine learning and side-channel analysis** to detect hidden information leakage in computational systems.


### Deep Learning Side-Channel Analysis Library

[https://github.com/LeakDetectAI/deep-learning-sca](https://github.com/LeakDetectAI/deep-learning-sca)

A Python library implementing **automated side-channel attacks using Neural Architecture Search (NAS)**.

Key features:

* automated leakage detection
* neural architecture search for attack models
* ranking loss optimization for key recovery
* scalable experimentation pipelines


### Automated Leakage Detection Experiments

[https://github.com/LeakDetectAI/automl-qild-experiments](https://github.com/LeakDetectAI/automl-qild-experiments)

This repository provides infrastructure for **automated information leakage detection experiments**, including:

* mutual information estimation
* AutoML-based leakage detection
* statistical leakage analysis
* large-scale experiment pipelines

The framework supports reproducible research and scalable experimentation across clusters.


# What We Will Build With Giveth Funding

Support from the Ethereum Security Quadratic Funding round will enable us to transform LeakDetect into a **production-ready security framework**.

## 1. Production-Ready Developer Toolkit

* Developer-friendly CLI
* SDK for leakage testing
* Integration with Ethereum wallets
* Integration with AI agent frameworks
* Plug-and-play leakage detection modules

## 2. Public Benchmarks and Datasets

* standardized leakage evaluation datasets
* reproducible research pipelines
* cross-chain testing environments
* benchmarking frameworks for wallets and agents


## 3. Ecosystem Integrations

LeakDetect will integrate with:

* wallet providers
* AI agent frameworks
* decentralized applications
* multi-chain systems


## 4. Security Metrics Standardization

LeakDetect will formalize measurable leakage metrics including:

* **Vulnerability Score (VS)**
* **Key Recovery Probability (KRP)**
* **Information Leakage Rate (ILR)**
* **Stealth Leakage Index (SLI)**

These metrics will enable **quantitative security analysis for decentralized systems.**


## 5. Community and Education

We will support ecosystem adoption through:

* developer documentation
* tutorials and guides
* workshops and presentations
* educational material on leakage-based attacks


# Why Donors Should Care

Leakage vulnerabilities represent a **public good security problem**.

They are:

* difficult to detect
* rarely measured
* widely overlooked
* potentially catastrophic at scale

Fixing them benefits the **entire ecosystem**, but the incentives to build such tooling are limited.

Your support helps:

• Protect user funds from next-generation attacks
• Secure AI-driven applications before mass adoption
• Strengthen Ethereum’s long-term resilience

This is exactly the type of **early, high-impact security work Quadratic Funding is designed to support.**


# Why Quadratic Funding Matters

Quadratic funding prioritizes **community support**, not just large donors.

This means:

* even small contributions matter
* more unique donors unlock more matching funds
* early momentum increases visibility and funding impact

Even a **$1–$10 donation** can significantly increase the project's matching allocation.


# Open Source Commitment

LeakDetect is designed as **open public infrastructure**.

Our commitments include:

* open source code
* public datasets
* transparent research
* reproducible experiments
* community collaboration

The goal is to build **shared security tooling for the Ethereum ecosystem**, not a closed product.


# Media and Demonstrations

Demo, screenshots, research publications, and slide decks:

[https://drive.google.com/drive/folders/1p1EAA8d-PDH-M_dFdcevmbqOE5mRMby4](https://drive.google.com/drive/folders/1p1EAA8d-PDH-M_dFdcevmbqOE5mRMby4)


# Website

[https://sites.google.com/view/sovralabs](https://sites.google.com/view/sovralabs)



# Repository Links

LeakDetectAI organization
[https://github.com/LeakDetectAI](https://github.com/LeakDetectAI)

Deep learning side-channel library
[https://github.com/LeakDetectAI/deep-learning-sca](https://github.com/LeakDetectAI/deep-learning-sca)

Leakage detection experiments
[https://github.com/LeakDetectAI/automl-qild-experiments](https://github.com/LeakDetectAI/automl-qild-experiments)



# The Bigger Vision

LeakDetect aims to redefine blockchain security.

From asking:

**“Is this system safe to run?”**

To asking:

**“Is this system safe to observe?”**

In open, adversarial environments like Ethereum:

**Anything observable can eventually be exploited.**

LeakDetect helps make these risks **measurable, detectable, and fixable.**



# Support LeakDetect

Support the project in the **Ethereum Security Quadratic Funding round on Giveth**.

Your contribution helps:

* surface an overlooked security risk
* protect Ethereum users
* strengthen the future of AI + blockchain systems

Even a small donation helps secure the ecosystem.


