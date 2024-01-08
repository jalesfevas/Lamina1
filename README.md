# Lamina1 Nodes
Requirements
```bash
CPU: Equivalent of 4 AWS vCPU
RAM: 8 GiB
SSD: 100 GiB
OS: Ubuntu 22.04
Port: 9671
```
Set Up Your Node
```bash
echo "deb [trusted=yes arch=amd64] https://snapshotter.lamina1.global/ubuntu jammy main" > /etc/apt/sources.list.d/lamina1.list && 
apt update && apt install lamina1-betanet
```
Start Node and Connect to LAMINA1
```bash
$ sudo systemctl status lamina1-node.betanet

*Output Example
● lamina1-node.betanet.service - Lamina1
     Loaded: loaded (/etc/systemd/system/lamina1-node.betanet.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-04-18 17:38:36 UTC; 21s ago
   Main PID: 2355 (lamina1.node)
      Tasks: 8 (limit: 1141)
     Memory: 335.8M
        CPU: 11.275s
     CGroup: /system.slice/lamina1-node.betanet.service
Apr 18 17:38:36 ip-172-31-83-52 systemd[1]: Started Lamina1.
```
Bootstrapping Process
```bash
$ lamina1.check-bootstrap.sh

*Output Example
{"jsonrpc":"2.0","result":{"isBootstrapped":true},"id":1}
{"jsonrpc":"2.0","result":{"isBootstrapped":true},"id":1}
{"jsonrpc":"2.0","result":{"isBootstrapped":true},"id":1}
```
If you want to add your node as a validator
```bash
- Connect with the L1 Staking Wallet to generate an L1 Betanet address
- Using the L1 Staking Wallet, check to make sure you have at least 31,337 L1 Betanet tokens on the P-chain. You can use the "cross chain" function to transfer your C-Chain or X-Chain tokens to the P chain.
- Use the L1 Staking Wallet to stake your tokens on your node ID
```
Get your node-id
```bash
$ lamina1.get_my_nodeid.sh
NodeID-[string]

*The returned NodeID-[string] is your unique node ID
```
