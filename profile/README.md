# Cabin Crew

### The Universal Chain of Custody for Autonomous Workflows.

Cabin Crew is the **Passport Office** for the AI Economy. We provide the infrastructure to run *any* agent (ours, yours, or third-party) with military-grade governance, identity verification, and immutable audit trails.

[**Website**](https://cabincrew.dev) • [**Documentation**](https://docs.cabincrew.dev) • [**The Manifesto**](https://aiagentmanifesto.org) • [**Discussions**](https://github.com/cabincrew-dev/.github/discussions)

---

## The Mission

As AI Agents move from "Chatbots" to "Action-Takers," the risk shifts from hallucination to **liability**.

Cabin Crew is an identity-agnostic orchestrator that wraps AI Agents in a cryptographically verified **"Black Box."** We ensure that every line of code written, every infrastructure plan generated, and every deployment executed is:

1.  **Identified:** Verified via OIDC (GitHub/AWS/GitLab).
2.  **Governed:** Checked against OPA Policies *before* execution.
3.  **Audited:** Sealed in a tamper-evident ledger.

## The Architecture

The platform follows a Hub-and-Spoke model decoupled by the **Cabin Crew Protocol**.

| Component | Role | Description |
| :--- | :--- | :--- |
| **[cabincrew-protocol](https://github.com/cabincrew-dev/cabincrew-protocol)** | **Protocol** | JSON Schemas defining the universal standard for Inputs, Artifacts, and Audit Logs. |
| **[cabincrew-action](https://github.com/cabincrew-dev/cabincrew-action)** | **Action** | The GitHub Action adapter that injects Identity and Configuration into the runtime. - **Coming Soon** |
| **[cabincrew-dev-engine](https://github.com/cabincrew-dev/cabincrew-dev-engine)** | **Agent** | Stateless agent that performs software development tasks such as fixing a bug - **Coming Soon**. |
| **[cabincrew-tdd-engine](https://github.com/cabincrew-dev/cabincrew-tdd-engine)** | **Agent** | Stateless agent that performs extreme programming practices for software development tasks such as creating a new feature - **Coming Soon**. |
| **[cabincrew-terraform-engine](https://github.com/cabincrew-dev/cabincrew-terraform-engine)** | **Agent** | Stateless agent that performs infrastructure as code tasks such as creating a new feature - **Coming Soon**. |
| **[cabincrew-bash-engine](https://github.com/cabincrew-dev/cabincrew-bash-engine)** | **Agent** | Stateless agent that performs shell tasks to enable functionality without needing to write code - **Coming Soon**. 

## Quick Start (Zero Config)

For Open Source repositories, Cabin Crew works out of the box to help with your code changes. Currently it supports bug fixes. Just comment `/fix` on a PR or on an Issue. More features are coming soon.

```yaml
# .github/workflows/cabincrew.yml
name: Cabin Crew
on:
  issue_comment:
    types: [created]

jobs:
  fly:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      id-token: write # Required for Audit Signing
      pull-requests: write
      issues: write
    steps:
      - uses: cabincrew-dev/cabincrew-action@v1
```



## The Protocol

We believe in Open Standards. The Cabin Crew Protocol is Apache 2.0.

Plan: Engines must calculate intent without side effects.

Govern: Policies check the intent against the organization's rules.

Apply: Engines execute the sealed plan.

Read the full specification at docs.cabincrew.dev.

## Community & Support

Have a question? Start a discussion in our Community Forum.

Found a bug? Open an issue in the specific repository.
