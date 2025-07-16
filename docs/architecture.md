# Architecture

## System Overview
GPUFlex distributes ML training tasks using federated learning over a decentralized set of GPU providers.

## Training Workflow
1. Consumer submits job
2. Data/model are sharded
3. Producers train on shards
4. Aggregator composes model

## Sharding & Distribution
GPUFlex partitions training data and optionally model segments to distribute across nodes.

## Aggregation & Verification
GPUFlex uses FedAvg, telemetry checks, and redundancy to validate results.