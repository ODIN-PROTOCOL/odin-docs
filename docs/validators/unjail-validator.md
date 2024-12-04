---
sidebar_position: 2
---

# How to Unjail a Validator

When a validator node is jailed, its operator must wait until the jail time has expired (see the jailing section of the FAQ for details) before sending an unjail transaction to the chain. To send an unjail transaction, follow these steps:

1. Run the `odind keys list` command to get the address of your jailed node. Save the address by copying it, then typing `ADDRESS=` followed by pasting the address. Press Enter.

2. Send an unjail transaction to the network using the following command:

    ```sh
    odind tx slashing unjail --from $ADDRESS --chain-id $CHAIN --node https://rpc.odinprotocol.io
    ```