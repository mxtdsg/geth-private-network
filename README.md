# geth-private-network

- - -

## Launch Geth Node
1. Need: geth
2. In the same directory, init genesis block
`$ geth --datadir ./user1(eg.) init ./genesis.json`
3. Launch geth node:
`$ geth --datadir ./user1  --networkid 987  --identity "user1"  --rpc  --rpccorsdomain "http://your_local_IP:8545"  --rpcapi "db,eth,net,web3,personal"`
4. Open another console, start a geth JS client, and attach it to `geth.ipc`:
`$ geth attach ipc_endpoint_url`
5. Some commands: 
`> personal.newAccount()`, `eth.coinbase`, `eth.getBalance(eth.coinbase)`, 
`miner.start(1)`, `miner.stop()`,

## Connect to MetaMask
`Import Account` with the json file inside `path_to_datadir/keystore`

## Connecting with Peers
1. find enode value: 
`> admin.nodeInfo.encode`
2. add peers to the network:
`> admin.addPeer(enode://value_above)` [::]:30303, replace [::]with local ip
3. some commands:
`admin.peers`, `net.peerCount`

## Resources
