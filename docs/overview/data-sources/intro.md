---
sidebar_position: 2
---

# Introduction

Odin's oracle system operates at its most fundamental level through data sources. These are **executable units** that outline the procedure for retrieving a particular type of data. To alleviate the computational burden and network latency that can impair on-chain performance, **data sources are executed off-chain**.

Data sources can access information through traditional APIs or other methods that produce the desired outcome. Openly accessible permissionless APIs permit anyone to inspect the data source, as well as any associated oracle scripts or applications that utilize it.

Odin's oracle system uses a unique verification system to ensure that the information provided by the data sources is accurate and reliable. When a data source is triggered, multiple validators are randomly selected to retrieve the data and compare the results. The data is deemed valid if the results are consistent across the majority of validators, and is then recorded on the blockchain for use in smart contracts and other applications. This decentralized approach to data verification helps to **prevent the introduction of faulty or malicious information, and strengthens the trustworthiness of the system as a whole**.