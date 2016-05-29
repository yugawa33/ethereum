# ethereum
privatechain

Congratulations for you initial your private node of Ethereum network.
Now let's start with the first Smart Contract.

Before we start, there are many resources you can refrence below:

* 	[Your first citizen: the greeter](https://github.com/ethereum/go-ethereum/wiki/Contract-Tutorial)
* 	[Writing a contract](https://ethereum.gitbooks.io/frontier-guide/content/writing_contract.html)
* 	[A 101 Noob Intro to Programming Smart Contracts on Ethereum](https://medium.com/@ConsenSys/a-101-noob-intro-to-programming-smart-contracts-on-ethereum-695d15c1dab4#.814nassq1)
* 	[Contracts and Transactions](https://github.com/ethereum/go-ethereum/wiki/Contracts-and-Transactions)
* 	[Oraclize’s documentation](https://docs.oraclize.it/#introduction)


There are only 3 Steps for us to play:

* 	Step 1) Install **Ethereum client** and **Ethereum Wallet**, Of course you need to start the node (run the geth and wallet).
* 	Step 2) Code the Smart Contract and Compile/Deploy to your network.
* 	Step 3) Verify your Smart Contract.


### Step 1 Install
It needs to install the **Ethereum client** and **Ethereum Wallet**. You can find the install guide as [Ethereum docs](https://github.com/yugawa33/ethereum/wiki/How-to-setup-Ethereum-multi-node-private-blockchain-for-testing). 
For the type of Ethereum client I select the go-ethereum client.


### Step 2 Coding/Compile/Deploy
Now there is the integration of Solidity and the Smart Contracts that work with Ethereum blockchains into Visual Studio 2015 Community, Professional, or Enterprise edition. This exists as an extension that is available [here](https://medium.com/@ConsenSys/solidity-integration-with-visual-studio-8bdab2ff8a74#.ko8g67ebl).
Or you can just use **Ethereum Wallet** to Coding/Compile/Deploy/Interact with your first Smart Contract. There is the sample code of Contract storage.

Create a new <datadir> folder in your system and deploy the nccugenesis.json(on the folder you launch geth) and static-nodes.json(on your datadir folder) files.

### Step 3 Launch
As the geth_nccu_cs.sh, remember change --datadir "<your datadir>"

```
geth --maxpeers 25 --genesis nccugenesis.json --networkid 104971 --port 33333 --rpc --rpccorsdomain "*" --datadir "<your datadir>"
```

After launch the first geth, please launch the secend geth as console mode to create new account and mine some NCCUCoin.
```
 geth attach
```

Creates a new account and prints the address. [Manage your accounts](https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts)
On the console, use:
```
> personal.newAccount("<your password for this account>")
```

Once your geth instance start to synchronisation, you do all things right.
```
I0401 12:43:12.738071   10636 downloader.go:288] Block synchronisation started
```

### Details for NCCUCoin private chain network

- Network Identity: **104971**
- All parameters same as Frontier except:
  - nccuinitGenesis.json (given below);
- Genesis block hash: `ee3898a932f04edff6de8b1b0eff3606b10f29e5bb2bb72a82e133b9fdae7194`
- Genesis head: `0x041eb9da8844a2d8b9b324d152d57cae91d15e907e1acab7d95d96414a64d50d`

### Seed Nodes
* "enode://115ebeacc211ff1007f3da0df5083c42b4ad763bbbbf90ece462ec596c336bd6b6edf753aae6f0287c93536d585ad01c71bb740c3e76b1b9e2c5c85631cad7e6@140.119.163.71:303033"
* "enode://61477080da895fb207556e60b24a8bb27adf22abd8dcaa4567f6bb395586e331fa6c43883d46ed4547e44f71bedb3b7d5974226b1ca9cb31982623336fe6ecfd@13.71.147.76:33333"
* "enode://c0721fea224c2e6018ba75bc57463f4c07e6e33e663adb0efae901dde9f90a8d63b97c37b889cd5d2d3b04e3188bb1510aeb0e5e579c864a4c9f339901113868@140.119.163.70:33333"

nccuinitGenesys.json
```nccuinitGenesys.json
{
  "nonce": "0x0000000000000042",
  "difficulty": "0x020000",
  "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "coinbase": "0x0000000000000000000000000000000000000000",
  "timestamp": "0x00",
  "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
  "extraData": "NCCU Private Ethereum Genesis Block",
  "gasLimit": "0x4c4b40"
}
```

static-nodes.json
```static-nodes.json
[
"enode://115ebeacc211ff1007f3da0df5083c42b4ad763bbbbf90ece462ec596c336bd6b6edf753aae6f0287c93536d585ad01c71bb740c3e76b1b9e2c5c85631cad7e6@140.119.163.71:303033"
,"enode://61477080da895fb207556e60b24a8bb27adf22abd8dcaa4567f6bb395586e331fa6c43883d46ed4547e44f71bedb3b7d5974226b1ca9cb31982623336fe6ecfd@13.71.147.76:33333"
,"enode://c0721fea224c2e6018ba75bc57463f4c07e6e33e663adb0efae901dde9f90a8d63b97c37b889cd5d2d3b04e3188bb1510aeb0e5e579c864a4c9f339901113868@140.119.163.70:33333"
]
```

### Getting NCCUCoin Ether
Start the miner you and while you [mined](https://github.com/ethereum/go-ethereum/wiki/Mining) some block, You can get some NCCUCoin Ether.

On the console, use:,
```
>miner.start(8)
```
And stop the miner
```
>miner.stop()
```

Enjoy and have fun.
Yogawa33
