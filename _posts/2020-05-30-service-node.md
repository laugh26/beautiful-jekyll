---
layout: post
title: Setup Service Node
subtitle: setup service node
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [service-node]
comments: true
---

A network of nodes hold a record of all the transactions made in a particular cryptocurrency. This record is called the ledger. Nodes which store and validate the ledger are referred to as full nodes.
Full nodes come to a consensus about the state of the blockchain by comparing transaction records and making sure they’re all the same. If they’re not, the odd node out is ignored and discarded from the network. This is important because it stops rule-bending and malicious activity like fake transactions.

To register as a Service Node, an operator creates a time-locked output of the required amount. In the extra field of the transaction, the Service Node operator includes the coinicles address which may receive Service Node rewards. This address will also be used as the public key for Service Node operations such as swarm voting.

Before each node joins the Service Node network, other nodes must individually validate that the said nodes collateral outlay matches the required amount, as per the decreasing collateralisation requirement. Although collateral transactions expire after 30 days, the wallet will have an opt-in automatic re-collateralisation feature.

1. Get a Server that meets requirements 

2. Run the Daemon on a server from a non-root user account, then stake from a local wallet (or a wallet on a separate server).

3. Connect via SSH to your server. 

4. add new user.

5. login to your new user account via SSH

6. Update necessary security patches and system utilities

7. Download & untar
 ```bash
   wget https://github.com/coiniclesdev/coinicle/releases/download/v7.0.0/coinicles-ubuntu18.04-v7.0.0.tar.1.gz.bz2

   tar -cjvf coinicles-ubuntu18.04-v7.0.0.tar.1.gz.bz2
  ```
8. Run Coinicles in a screen and Detach

   Screen <enter>

   cd coinicles-ubuntu18.04-v7.0.0
   ```bash
   ./coiniclesd --service-node --storage-server-port 23434 --service-node-public-ip <your-ip>
   ```
   Ctrl +AD

9. Open a Wallet

This wallet can be in a screen on the Service Node machine, or a wallet on your local computer (assuming you have downloaded the binaries).

**Note:** Do not keep your feed in the same machine as the service node.
{: .box-error}

cd coinicles-ubuntu18.04-v7.0.0

Linux/MAC - ./coinicles-wallet-cli Windows - coinicles-wallet-cli

Enter Name: Name your wallet

Enter password

Language: 1 (for English)

Securely store: 1. Address 2. Seed Phrase 3. Pass-phrase

Send enough Coinicles to fund a node, wait for Balance to be unlocked (5 confirmations)

10. Register your Service Node

On your Service Node reattach to the screen which has the Service Node running.

screen -r

prepare_registration

Contribute entire Stake: Y/N

Enter Coinicles Address

Enable Restaking: Y/N

Confirm: Y

Copy green registration message

Ctrl +AD

11. Reattach to Service Node or local wallet

Paste in registration message <enter>

12. Attach Back to Service Node Daemon

screen -r

print_sn_key

Copy service node key, and search for it on: https://coinicles.tech/service_nodes

CTRL +AD

ctrl +ad detaches screen and runs your Coinicles Service Node in background this is critical


