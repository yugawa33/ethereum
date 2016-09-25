Ethereum

Welcome to the NCCUCoin LAB on Ethereum network.

For develop the DApp on Ethereum, It needs to setup a private blockchain with multi-nodes, so that we can test smart contracts as per tutorials.

There are only 3 Steps for us to play:
* 	Step 1) Install **Ethereum client** and **Ethereum Wallet(Optional)**.
* 	Step 2) Create a new <datadir> folder in your system and deploy the [nccugenesis.json] and [static-nodes.json] files.
* 	Step 3) Launch the geth client [geth_nccu_cs.sh] and mine some NCCUCoin.

### Step 1 Install
It needs to install the **Ethereum client** and **Ethereum Wallet**. You can find the install guide as [Ethereum docs](http://www.ethdocs.org/en/latest/ethereum-clients/choosing-a-client.html#installing-a-client). 
For the type of Ethereum client I select the go-ethereum client.

After install the Ethereum client, If you just want to launch your private chain as yourself and not to connect to other node. 
More information about as [Command Line Options](https://github.com/ethereum/go-ethereum/wiki/Command-Line-Options).
In the parameter of --networkid value is Network identifier (integer, 0=Olympic, 1=Frontier, 2=Morden) (default: 1), you can choose any value as your private network. We choose '104'+'971' as 'chain create at chinese year'+'NCCU department code'.
Now you can run the geth instance as the scipt below:

```
 geth --networkid <any number for your private network> --datadir "<your datadir folder>"
```

Or connect to real Ethereum network
```
 geth 
```

Or connect to test Ethereum network
```
 geth --testnet
```

After launch the first instance of geth, You can also launch the second or more geth instance as console mode. with this ocnsole mode you can trigger the mine process or creat new account.
```
 geth attach
```


### Step 2 Setup
Create a new <datadir> folder in your system and deploy (copy these 2 *.json file from the code list above) the nccugenesis.json to the folder you launch geth and static-nodes.json(on your datadir folder) files. The more information about the genesis block can reference by [Ethereum Yellow Paper -- 4.4. The Block](http://gavwood.com/Paper.pdf) and [Custom Genesis Block](http://blog.carl.pro/2015/09/setup-a-local-ethereum-test-blockchain/). Run the command to init it:

```
geth init nccugenesis.json
```


### Step 3 Launch
As the geth_nccu_cs.sh, remember change --datadir "<your datadir>"

```
geth --maxpeers 25 --networkid 104971 --port 33333 --rpc --rpccorsdomain "*" --datadir "<your datadir>"
```

After launch the first geth, please launch the secend geth as console mode to create new account and mine some NCCUCoin.
```
 geth attach
```

Creates a new account and prints the address. [Manage your accounts](https://github.com/ethereum/go-ethereum/wiki/Managing-your-accounts)
On the console, use the script and you will get a new address with return:
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
* "enode://115ebeacc211ff1007f3da0df5083c42b4ad763bbbbf90ece462ec596c336bd6b6edf753aae6f0287c93536d585ad01c71bb740c3e76b1b9e2c5c85631cad7e6@140.119.163.71:30303"
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
