---
title: Resume
description: 
permalink: 
tags:
  - personal
draft: false
created: 2024-12-12, 20:49
updated: 2026-10-17, 02:14
---
## Experience

### Independent
*Independent Developer (Taipei, 2026/07 – now)*
- Built open-skills, an open-source Claude Code plugin with six skills for coding agents.
- Built a code review pipeline: three reviewers check a change in parallel, each finding is verified against the code before it is reported, and the result is ranked by severity with a verdict on the design.
- Built a skill that handles PR/MR review comments on GitHub and GitLab: checks each comment against the code, fixes the valid ones and drafts rebuttals with evidence for the rest.
- Built an interactive codebase walkthrough that reads code in a git worktree pinned to a commit, cites every stop as `file:line`, and saves a reading record.
- Built a harness for agent development: `init` scaffolds the project's CLAUDE.md and long-term memory, `harness-flow` dispatches work to an implementor agent and marks it done only after a reviewer agent passes it, `handoff` saves decisions, dead ends and next steps so a fresh session can resume.
- Published an article on using git worktree to run parallel development, including multiple coding agent sessions on one repo.
- Stack: Claude Code plugins, agent skills, subagents, Git, GitHub CLI, GitLab CLI

### BSOS - Isle Finance
*Blockchain Developer (Remote, 2025/08 – 2026/06)*
- Built a DeFi lending protocol from zero to mainnet: users borrow credit-card spending limits against on-chain collateral.
- Owned the architecture, the Solidity contracts and the full test suite.
- Redesigned liquidation with partial liquidation and a grace period.
- Defined risk parameters and ran internal security reviews.
- Built the on-chain indexer with The Graph, Ponder and Envio.
- Stack: Solidity, Foundry, TypeScript, DeFi Lending, The Graph, Ponder, Envio

### Rootz Labs - Pencils Protocol
*Blockchain Developer (Remote, 2024/05 – 2025/01)*
- Designed and shipped a leveraged yield farming protocol on Scroll, from zero to mainnet, and upgraded it after launch. Peak TVL was over $300M.
- Coordinated external audits and hardened the protocol's security.
- Researched lending, DEX and auction mechanisms.
- Stack: Solidity, Foundry, Leveraged Yield Farming, Lending/DEX/Auction

### FiO
*Blockchain Developer (Taiwan, 2021/02 – 2023/12)*
- Researched Transparent Proxy and UUPS to keep contracts upgradeable as the product changed.
- Introduced an upgradeable architecture so the team could iterate without redeploying.
- Built ERC20 staking systems and an ERC721 marketplace.
- Stack: Solidity, Foundry, Hardhat, ERC20, ERC721, Upgradeable Proxy (Transparent/UUPS)

---

## Speaking

### COSCUP 2022
*Migrate to Foundry*
- Introduce Foundry framework for solidity development
- https://coscup.org/2022/zh-TW/session/8WTFTY

### COSCUP 2024
*A short experience to perform fuzzing and formal verification*
- Introduce and perform fuzzing testing and formal verification in solidity development.
- Tools: Foundry Invariants, Echidna, Halmos
- https://coscup.org/2024/zh-TW/session/KHKQTP
