# Key Concepts

### Federated Learning

Federated learning (FL) is a machine learning approach that enables model training across multiple decentralized devices or servers without pooling all the data in one place . In traditional training, you would gather all your training data on a central server; with federated learning, by contrast, each node (e.g. a GPUFlex worker) trains on its local dataset and only shares model updates (weight adjustments) rather than raw data. This allows collaborative model training while preserving data privacy and reducing the need to transmit large datasets. GPUFlex leverages federated learning techniques to train AI models across many distributed GPUs. The system coordinates training rounds where each worker node computes an update to the model, and a central aggregator merges these updates into a global model (see Federated Averaging in the Architecture section). Federated learning makes GPUFlex’s distributed training efficient – it minimizes data transfer and lets each GPU work on a shard of the data in parallel, all contributing to a shared model.

### Decentralized Physical Infrastructure Network (DePIN)

DePIN stands for _Decentralized Physical Infrastructure Network_. This concept refers to networks that use blockchain and crypto incentives to coordinate physical hardware resources (like devices, sensors, or compute nodes) in a decentralized way . In a DePIN, participants collectively operate an infrastructure by contributing resources and are rewarded for their contributions. Famous examples include Helium (for wireless hotspots) and Filecoin (for storage), where individual operators power the network and earn tokens. GPUFlex is an example of a DePIN for GPU compute: it connects physical GPU hardware from many owners into one network, using blockchain-based tokens to incentivize participation. By leveraging a DePIN model, GPUFlex creates a community-driven GPU cloud where no single entity controls the hardware. The network harnesses the _“long tail”_ of idle capacity – all the scattered GPUs people already own – and unites them to provide valuable compute services. Participants who provide GPU power earn rewards, and those who need compute pay for it, all mediated by smart contracts in a trust-minimized way.



### XP-Based Incentive Layer (Potential future)

In addition to token rewards, GPUFlex introduces an XP-based incentive layer. “XP” stands for experience points – a mechanism to quantify and reward a node’s positive contributions over time. Whenever a GPUFlex worker node successfully completes training jobs and submits valid results, it earns XP points in proportion to the work done (and possibly the quality of results). A node’s accumulated XP reflects its reputation and reliability in the network. This serves several purposes:

* Reputation and Trust: Nodes with higher XP have a proven track record, making them more likely to be selected for new jobs. This encourages consistent, honest behavior, since cheating or underperforming would prevent earning XP (or even lead to loss of XP).
* Incentive Alignment: XP works alongside financial rewards to motivate long-term participation. While the GPUX token provides immediate monetary reward, XP provides a longer-term reward (e.g. unlocking higher-tier tasks or bonus payments), aligning node operators with the network’s success.
* Sybil Resistance: By tying reputation to work, XP makes it harder for someone to spin up fake multiple nodes to game the system. Only genuine, productive work builds XP, so attackers can’t easily fast-track many malicious nodes without doing real work.

The XP-based incentive layer adds a gamified element to GPUFlex’s economy. It effectively _“levels up”_ reliable providers, creating a merit-based system on top of the token economics. This extra layer helps maintain trust in a permissionless network of anonymous GPU providers.



### GPUX Token (Potential future)

The GPUX token is the native cryptocurrency of the GPUFlex platform and the backbone of its economy. GPUX serves several key functions:

* Payment for Compute: Consumers who want to train models pay for jobs in GPUX. The cost is calculated based on the amount of GPU time and resources required. This payment goes into a smart contract escrow for the duration of the job.
* Provider Rewards: GPU owners (providers) earn GPUX tokens as compensation for completing training work. When a training job finishes successfully, the escrowed GPUX is released and distributed to the participating worker nodes, proportionate to their contribution.
* Incentivization: Token rewards motivate individuals and organizations to contribute their hardware to the network. As seen in other decentralized compute marketplaces, participants are willing to share resources when they are compensated in tokens . GPUX creates a market-driven supply of compute power by aligning economic incentives.
* Governance and Staking (Future): In a mature GPUFlex ecosystem, GPUX may also be used for governance decisions (allowing token holders to vote on protocol changes) or for staking mechanisms (e.g. requiring nodes to stake some GPUX as collateral to discourage malfeasance). These features ensure that GPUX isn’t just a utility token but also secures and guides the network as it grows.

By using the GPUX token, GPUFlex establishes a self-sustaining economy: those who need AI compute buy GPUX to pay for jobs, driving demand, while those with spare GPU capacity earn GPUX by supplying compute, increasing token distribution. This model follows the proven playbook of decentralized infrastructure networks – contributors are financially rewarded in the network’s native token, which they can use or trade freely . The GPUX token thus underpins the value exchange between AI users and GPU providers, enabling a truly decentralized GPU cloud.

***
