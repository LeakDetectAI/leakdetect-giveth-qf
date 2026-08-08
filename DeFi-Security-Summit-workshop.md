# The Trillion-Dollar Attack Surface

## Security Beyond the Smart Contract

**Manu Sheel Gupta**

---

### Opening

When we talk about DeFi security, we usually talk about smart contracts.

We audit the Solidity.

We fuzz the contracts.

We look for reentrancy, oracle manipulation, access-control bugs, signature replay, flash-loan attacks and economic exploits.

And that work is absolutely necessary.

But I want to argue today that **we are securing only part of the system.**

Because a modern DeFi transaction is no longer simply:

**User → Smart Contract**

It increasingly looks more like:

**User → Agent → Wallet → Dapp → Ethereum → P2P Network**

And every one of those layers observes something.

Every layer makes decisions.

Every layer can leak information.

And increasingly, information leaked at one layer can be used to attack another.

That is the security problem I want to explore today.

---

# 1. The DeFi security model is changing

For the first generation of DeFi, the dominant security question was:

> **“Can someone make the smart contract do something it wasn't supposed to do?”**

That gave us an enormous security ecosystem around smart contracts.

But now we have wallets that simulate transactions.

Dapps that predict user behavior.

MEV infrastructure that observes pending transactions.

Bridges and cross-chain protocols that coordinate multiple systems.

Privacy-preserving applications.

Autonomous agents that can decide what transactions to execute.

And increasingly sophisticated P2P infrastructure underneath Ethereum and the applications built around it.

So the question becomes:

> **What can an attacker learn before, during and after a transaction—and what can they do with that information?**

This is a different security model.

It is a **leakage model**.

---

# 2. Think about the entire security stack

Imagine a single user interacting with a DeFi application.

At the top we have the **user**.

Below the user we may have an **autonomous agent** deciding what action should be taken.

Then a **dapp** constructs the transaction.

A **wallet** simulates, signs and broadcasts it.

The transaction enters **Ethereum**.

And beneath Ethereum is a distributed networking stack involving nodes, peers, discovery mechanisms, gossip, transports and other P2P infrastructure.

So our security stack looks something like:

**Users**
↓
**Autonomous Agents**
↓
**Dapps**
↓
**Wallets**
↓
**Ethereum**
↓
**P2P / libp2p Infrastructure**

Traditionally, we analyze these layers separately.

Agent security is one field.

Wallet security is another.

Smart-contract security is another.

Network security is another.

Privacy research is another.

But attackers don't respect those boundaries.

---

# 3. Leakage is the connective tissue

Consider a simple example.

Suppose an autonomous trading agent decides:

> “I am going to execute a large position.”

The agent may reveal information through its behavior before the transaction is executed.

The dapp may expose additional information through RPC requests.

The wallet may simulate the transaction.

The transaction may propagate through the network.

Nodes may observe timing, propagation patterns or other metadata.

And eventually the transaction becomes visible on-chain.

None of these individual observations necessarily constitutes a vulnerability.

But when combined, they can become one.

This is what I call **cross-layer leakage**.

The attacker doesn't necessarily need to break cryptography.

They don't necessarily need to compromise the wallet.

They don't necessarily need to exploit the smart contract.

They can simply **correlate observations across layers.**

---

# 4. Security is not just about what we protect

This leads to an important distinction.

There are three questions we should ask about every decentralized system:

### What does the system expose?

What data becomes observable?

### What does the system infer?

What information can an observer reconstruct from that data?

### What can the observer do with that information?

Can it front-run?

Can it identify users?

Can it infer trading strategies?

Can it deanonymize participants?

Can it manipulate an agent?

Can it predict future actions?

Can it selectively disrupt communication?

The third question is where privacy becomes security.

---

# 5. Autonomous agents make this much harder

Now let's introduce autonomous agents.

An agent can continuously observe its environment, reason about opportunities and execute transactions.

That creates an entirely new security surface.

A traditional wallet waits for a user to sign.

An autonomous agent may make hundreds or thousands of decisions.

That means the agent's:

* prompts,
* observations,
* decisions,
* transaction construction,
* timing,
* retries,
* failures,
* counterparties,
* and communication patterns

can all become security-relevant signals.

An attacker may not need to steal the agent's private key.

They may only need to learn enough about **what the agent is trying to do.**

This creates a new class of questions:

> Can we infer an agent's strategy from its network behavior?

> Can we distinguish one agent from another?

> Can we identify the user's intent before execution?

> Can we manipulate an agent through information supplied by its environment?

> Can network-level observations reveal application-level state?

These are not purely AI-security questions.

And they are not purely DeFi-security questions.

They sit at the intersection.

---

# 6. Wallets are becoming security boundaries

Wallets have historically been treated primarily as key-management systems.

But modern wallets are increasingly becoming **decision engines**.

They simulate transactions.

They estimate fees.

They interact with multiple RPC providers.

They communicate with dapps.

They may use policy engines.

They may incorporate AI or agentic functionality.

And they increasingly mediate the user's intent.

That means wallet security must evolve from:

**“Can someone steal the key?”**

to:

**“Can someone manipulate what the key holder believes they are signing?”**

This is a fundamentally different threat model.

A perfectly secure private key can still be used to execute a malicious transaction if the surrounding system has been manipulated.

---

# 7. The network is part of the security model

This brings us to a layer that is often invisible to application developers:

**the network.**

Decentralized applications don't magically communicate.

They depend on networking infrastructure.

Ethereum nodes discover peers.

Messages propagate.

Transactions are relayed.

Protocols establish connections.

Nodes maintain routing and peer information.

And all of that creates metadata.

At the P2P layer, we can potentially observe things like:

* timing,
* connection patterns,
* peer relationships,
* propagation paths,
* message frequency,
* transport characteristics,
* failures,
* retries,
* and network topology.

Again, none of this necessarily contains the user's private key.

But metadata can be incredibly powerful.

---

# 8. Metadata can become an attack primitive

Imagine an attacker cannot decrypt a user's communication.

They don't need to.

Suppose they can determine:

> “This node is probably the origin of this transaction.”

Or:

> “This wallet is interacting with this application.”

Or:

> “This agent behaves differently immediately before making a large trade.”

Or:

> “These peers tend to receive particular messages earlier than others.”

Now combine that with public blockchain information.

Suddenly, seemingly harmless network observations can be correlated with on-chain activity.

This is where **network privacy becomes financial security.**

---

# 9. The problem with siloed security research

Today we often have excellent security researchers working on each individual layer.

Smart-contract researchers.

Wallet researchers.

MEV researchers.

Privacy researchers.

AI security researchers.

P2P researchers.

But we rarely evaluate the **composition of those layers.**

And that is where I think one of the biggest research opportunities lies.

Because a system can be secure at every individual layer and still be insecure as a whole.

Let me repeat that:

> **A collection of individually secure components does not necessarily produce a secure system.**

The leakage can happen at the interfaces.

---

# 10. Introducing cross-layer leakage analysis

The research direction we are developing is based on a simple idea:

**Stop analyzing leakage in isolation.**

Instead, build datasets and experiments that connect observations across the stack.

For example:

**Agent behavior**

↓

**Dapp interaction**

↓

**Wallet simulation**

↓

**Transaction construction**

↓

**Transaction propagation**

↓

**On-chain execution**

We can then ask:

> How much information about the original intent can an observer reconstruct?

This turns a philosophical privacy question into something measurable.

---

# 11. From anecdotes to measurements

The goal is not simply to say:

> “This system leaks metadata.”

We need to quantify it.

We want reproducible experiments.

Controlled environments.

Common datasets.

Attack scenarios.

Metrics.

Baselines.

And mitigation experiments.

For example, we can ask:

### Identification

Can we identify a particular user, wallet or agent?

### Inference

Can we infer what action they are about to perform?

### Correlation

Can observations from two different layers be linked?

### Prediction

Can future behavior be predicted?

### Attribution

Can we determine the origin of an action?

### Exploitation

Can that information actually produce an economic or security advantage?

This gives us a path toward a **measurement framework for decentralized-system leakage.**

---

# 12. The trillion-dollar question

Why does this matter so much?

Because DeFi isn't just holding tokens anymore.

It is becoming infrastructure for:

* financial markets,
* payments,
* stablecoins,
* lending,
* derivatives,
* autonomous agents,
* identity,
* decentralized storage,
* cross-chain systems,
* and increasingly machine-to-machine commerce.

The value secured by these systems is enormous.

So even a small amount of exploitable information can have disproportionate economic consequences.

The attack surface is therefore not simply:

**“How do we protect the contract?”**

It is:

> **“How do we protect the entire information flow that surrounds financial execution?”**

---

# 13. What would a practical security stack look like?

I think we need at least five capabilities.

### 1. Measurement

We need to know what systems actually reveal.

### 2. Cross-layer correlation

We need to understand what can be inferred by combining observations.

### 3. Adversarial evaluation

We need attackers attempting to reconstruct information, not merely researchers inspecting protocols.

### 4. Mitigation

We need practical techniques that reduce leakage without destroying usability or decentralization.

### 5. Continuous monitoring

Security cannot be a one-time audit.

The system changes.

Agents change.

Dapps change.

Network conditions change.

New correlations emerge.

---

# 14. This is where P2P research becomes DeFi security

For people working primarily in DeFi, the P2P layer can feel very far away.

But it isn't.

The P2P network is part of the execution environment.

If the network can reveal information about transaction origin, timing or behavior, then the network is participating in the security model of the financial application.

This is why work on networking protocols such as **libp2p** is relevant to application security.

Not because P2P replaces smart-contract security.

But because **security boundaries increasingly cross protocol boundaries.**

---

# 15. What we want to build

The research initiative we're developing is structured around three milestones.

### First: Expand the datasets

Collect reproducible observations across:

* wallets,
* dapps,
* agents,
* Ethereum,
* P2P networks,
* privacy systems,
* and DeFi workflows.

### Second: Perform cross-domain analysis

Look for correlations that are invisible when each dataset is analyzed independently.

### Third: Develop practical mitigations

Once we can reproduce a leakage path, we can ask:

> How do we reduce it?

Potentially through changes in:

* transaction handling,
* wallet architecture,
* agent design,
* RPC infrastructure,
* networking protocols,
* privacy mechanisms,
* or application architecture.

The objective is not merely to publish vulnerabilities.

It is to produce **engineering guidance that developers can actually use.**

---

# 16. A new security discipline

I think this points toward a broader discipline:

## Decentralized Systems Leakage Security

The unit of analysis is not just the contract.

It is the **system.**

The attacker is not necessarily a single compromised component.

It may be an observer correlating multiple weak signals.

And the security property isn't simply:

> “Nobody can steal the key.”

It is also:

> “An adversary cannot infer sufficiently sensitive information from the system's observable behavior to gain an unacceptable advantage.”

That is a much more ambitious security objective.

---

# 17. Three questions for every DeFi system

So I want to leave you with three questions.

### Question 1

**What can an observer see?**

Not just on-chain.

Look at the wallet.

The RPC layer.

The dapp.

The agent.

The network.

### Question 2

**What can they infer by combining those observations?**

A single data point may be harmless.

Ten correlated data points may reveal the strategy.

### Question 3

**Can that inference become an economic attack?**

If the answer is yes, we have a security problem.

---

# Closing

The next generation of DeFi security will not be won by securing one layer better in isolation.

It will be won by understanding **how information moves between layers.**

From the user's intent,

to the autonomous agent,

to the dapp,

to the wallet,

to Ethereum,

to the P2P network,

and back again.

We need to identify what decentralized systems unintentionally reveal.

We need to make that leakage measurable.

We need reproducible attacks.

And most importantly, we need practical mitigations before information leakage becomes a security or privacy incident.

Because in a system securing potentially trillions of dollars,

**the information surrounding a transaction can be almost as valuable as the transaction itself.**

That is the trillion-dollar attack surface.

And that is the security problem we should start measuring now.
