# Chain Integration Proposal

## Overview

### Project Overview

- **Chain Name:** Stacks
- **Project Description:** Stacks is the leading Bitcoin Layer-2, enabling smart contracts and decentralized applications to use Bitcoin as a secure base layer. Stacks extends the capabilities of Bitcoin without changing Bitcoin, unlocking billions in latent capital.
- **Proposer:** Buidly (on behalf of Trust Machines)
- **Contact Information:**
  - **Stacks Website:** https://trustmachines.co/
  - **Buidly Website:** https://www.buidly.com/

### Chain Overview

#### At-A-Glance

- **Justification for Stacks:** Integrating Stacks with the Axelar network will significantly enhance interoperability across blockchain ecosystems, creating seamless cross-chain communication and asset transfer capabilities.
Stack's Clarity based smart contract platform, combined with Axelar's secure and scalable infrastructure, will provide developers and users with new opportunities for decentralized finance (DeFi), asset tokenization, especially involving sBTC, Stack's non-custodial, programmable 1:1 Bitcoin-backed asset.
This integration will allow Stack's ecosystem to expand its functionality, gain access to broader liquidity, and facilitate interactions with other blockchains.
- **Management Team Credentials:** The Stacks ecosystem is decentralized with many independent entities working to build out the protocol as well as build applications and services on top of it. Among the most important entities are the [Stacks Foundation](https://stacks.org/) and [Trust Machines](https://trustmachines.co/).  
- **Notable Use Cases:**
    - **sBTC**: [sBTC](https://www.stacks.co/sbtc) unlocks Bitcoin, allowing users to earn yield, access on-chain lending, and trade on decentralized exchanges.
    - **Granite**: [Granite](https://granite.world/) is a Bitcoin Liquidity Protocol that provides the first truly non-custodial, secure, and decentralized way to borrow against Bitcoin.
    - **Zest**: [Zest Protocol](https://www.zestprotocol.com/) is an open-source, on-chain lending platform built for Bitcoin, allowing users to earn or borrow against their BTC.
    - **ALEX**: [ALEX](https://alexlab.co/) is Next Gen DeFi on Bitcoin via Stacks. Building Financial Infrastructure on Bitcoin through Stacks

#### Technology Overview

Stacks is a pioneering Bitcoin layer-2 blockchain that brings smart contract functionality to the Bitcoin ecosystem without requiring any modifications to the base layer. By leveraging Bitcoin's security and adding programmability through its innovative architecture, Stacks has positioned itself as a significant player in expanding Bitcoin's utility beyond simple value transfer.

- **Protocol Overview:**
	- **Consensus Mechanism:** Stacks implements an innovative consensus mechanism called Proof-of-Transfer (PoX), which is an extension of the Proof-of-Burn (PoB) mechanism. In PoX, miners transfer Bitcoin to selected network participants rather than burning tokens, as is common in PoB systems. This mechanism creates a connection between Stacks and Bitcoin where:
        - Miners transfer Bitcoin that's used to provide Stacking rewards to STX token holders who help secure the network.
        - "Stackers" lock up their STX tokens for specific periods and provide their BTC addresses to receive rewards in Bitcoin.
        - By reusing the energy that Bitcoin has already expended via its Proof-of-Work mechanism, PoX is more energy-efficient than creating a new PoW chain.
        - PoX solves the programmability limitations of PoW while enjoying the security benefits provided by the Bitcoin blockchain.
	- **Smart Contract Platform:** Stacks uses its own smart contract language called Clarity. This purpose-built programming language was specifically designed for creating secure smart contracts on the Stacks blockchain. Clarity was designed with security as a primary consideration to prevent many of the exploits and bugs that have plagued other smart contract platforms.
- **Transaction Finality:** Internal transactions that don't rely on Bitcoin state, and thus won't change if Bitcoin forks have faster confirmations of 1 block. Stacks transactions are settled on Bitcoin, users benefit from Bitcoin's security guarantees. Stacks blocks have 100% Bitcoin finality, they are as hard to reverse as Bitcoin transactions themselves.
- **Additional Notable Features:**
    - **sBTC**: sBTC is a decentralizedl 1:1 Bitcoin-backed asset on the Stacks Bitcoin Layer
    - **Bitcoin Connection**: Developers can access the state of the Bitcoin chain using the Clarity smart contract language

#### Security Considerations

Clarity is a decidable smart contract language that optimizes for predictability and security, designed for the Stacks blockchain. The design decisions behind Clarity were based heavily on taking lessons learned in common Solidity exploits and creating a language that has been purpose-built for safety and security in mind. Clarity is interpreted, not compiled, does not permit reentrancy and guards against overflow and underflows. 

On Stacks, transactions are secured by post conditions, instead of the approve/transfer flow of EVM chains. Post conditions can be attached to transactions to assert the chain state has changed in a certain way once the transaction has completed. For example, a user calling into a smart contract may attach a post condition that states that after the call completes, exactly 500 STX should have been transferred from one address to another. If the post condition check fails, then the entire transaction is reverted. Since custom token support is built right into Clarity, post conditions can also be used to guard any other token in the same way.

### Axelar Integration Components

- **External Gateway Contracts:** The Clarity contracts for the Stacks blockchain were developed by Trust Machines and are available at https://github.com/Trust-Machines/stacks-axelar
- **Amplifier Contracts:** The Amplifier Contracts & Ampd module were developed by Buidly. The contracts can be found in the [Trust Machines Axelar Amplifier](https://github.com/Trust-Machines/axelar-amplifier/tree/stacks_contracts_v2) fork, while the Ampd Stacks handlers were merged into the [Axelar Amplifier](https://github.com/axelarnetwork/axelar-amplifier/pull/728) repository 

## Request for the Amplifier Advisory Committee Review

### Purpose

The purpose of this review is to ensure that the integration of Stacks with the Axelar network adheres to all security and technical standards, ensuring a secure and efficient connection.

### Additional Information

- **GitHub Repository:** https://github.com/stacks-network/stacks-core
- **Developer Documentation:** https://docs.stacks.co/
- **Whitepaper:** https://stacks-network.github.io/stacks/stacks.pdf
- **Independent Audit Reports:** https://stacks.org/audits
- **Stacks Axelar Contracts Report:** [Clarity Alliance](https://github.com/Clarity-Alliance/audits/blob/main/Clarity%20Alliance%20-%20Axelar.pdf)
- **Stacks Axelar Amplifier Report:** [FYEO v1.0](https://github.com/fyeo-io/public-audit-reports/blob/main/Code%20Audit%20Reports/2025/Axelar/Axelar%20-%20Security%20Code%20Review%20of%20Axelar%20Stacks%20v1.0.pdf)

## Community Involvement

### Discussion Forum

Community members are encouraged to participate in the discussion and provide feedback on this proposal through the Axelar community forum.

### Voting

Following the Amplifier Advisory Committee's review, a community vote will be held to determine the approval of Stacks integration with the Axelar network.

### Feedback and Questions

For any questions or feedback regarding this proposal, please contact Buidly at [contact@buidly.com](contact@buidly.com) or via Telegram at [@buidly](https://t.me/buidly). 
