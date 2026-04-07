# Gravity Well Protocol

An edge-native coordination protocol for the Cocapn Fleet. It helps distributed agents discover each other, share state efficiently, and detect failures without a central server.

---

## Why this exists
Agent coordination systems often assume datacenter conditions: stable latency, high bandwidth, and a central controller. This doesn't work for agents running across thousands of global edge locations.

Gravity Well provides a quiet, network-efficient way for agents to stay aware of each other at the edge.

---

## Quick Start
1. **Fork** this repository.
2. **Deploy** it to a Cloudflare Worker or compatible edge runtime.
3. **Configure** the protocol parameters for your network.

**Live Demo:** Join the public test fleet at [the-fleet.casey-digennaro.workers.dev](https://the-fleet.casey-digennaro.workers.dev)

---

## How it Works
- **Autonomous Region Broadcasts (ARBs)**
  Agents broadcast state updates only within a defined local region (e.g., based on latency or geography), not across the entire network.

- **Eigenvector Gossip**
  State propagates along established network paths derived from traffic patterns, which can significantly reduce bandwidth compared to random peer selection.

- **Ghost Detection**
  Identifies unresponsive or latent nodes by analyzing patterns in normal gossip traffic, avoiding explicit heartbeat messages.

- **Built for the Edge**
  The reference implementation is a single file with zero dependencies, designed for the constraints of edge runtimes like Cloudflare Workers.

---

## One Honest Limitation
The protocol's efficiency depends on having a reasonable view of network adjacency or traffic patterns. In a completely opaque or extremely chaotic network, its benefits may diminish.

---

## What to Expect
- No required global consensus or voting mechanism.
- No proprietary runtime; it runs anywhere JavaScript runs.
- A testable protocol specification designed for modification and research.
- Clean extension points for your own logic (adjacency matrices, trust scores, detection heuristics).

---

## Contributing
This project follows a fork-first philosophy. You are encouraged to fork the repository, run your own network, and submit pull requests or issues based on your findings.

---

MIT License

Superinstance & Lucineer (DiGennaro et al.).

---

<div>
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> · <a href="https://cocapn.ai">Cocapn</a>
</div>