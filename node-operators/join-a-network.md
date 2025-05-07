---
description: >-
  This guide includes full instructions for joining the testnet and mainet
  (coming soon)  either as an archive/full node or a pruned node.
---

# Join a Network

Instructions for boosterizing a node using [State Sync.](join-a-network.md#state-sync)

For instructions to join as a validator, please also see the [Validator Guide](becoming-a-validator/).

### Overview

* [Getting Started](join-a-network.md#getting-started)
* [Choosing a Network ](join-a-network.md#choosing-a-network)
* &#x20;[Explorers](join-a-network.md#explorers)
* [Hardware Requirements](join-a-network.md#hardware)
* [General Configuration](join-a-network.md#general-configuration)
  * [Initialize Chain](join-a-network.md#initialize-chain)
  * [Seeds & Peers](join-a-network.md#seeds-and-peers)
  * [Pruning of State](join-a-network.md#pruning-of-state)
  * [REST API](join-a-network.md#rest-api)
  * [GRPC](join-a-network.md#grpc)
* [Sync Options](join-a-network.md#sync-options)
  * [Blocksync](join-a-network.md#blocksync)
  * [State Sync](join-a-network.md#state-sync)
  * [Quick Sync](join-a-network.md#quicksync)&#x20;
* [Snapshots](join-a-network.md#snapshots)
* [Cosmovisor](join-a-network.md#cosmovisor)
* [Running via Background Process](join-a-network.md#running-via-background-process)
* [Exporting State](join-a-network.md#exporting-state)
* [Verify ](join-a-network.md#verify-testnet)[network](join-a-network.md#verify-network)

## Getting Started

Make sure the following prerequisites are completed:

* Choose the proper hardware/server configuration. See the [hardware guide](join-a-network.md#hardware).
* Ensure crossfid is properly installed. See the [installation guide](join-a-network.md#general-configuration) for a walkthrough.
* Follow the [configuration guide](join-a-network.md#general-configuration) to intialize and prepare the node to sync with the network.



***

### Choosing a Network&#x20;

The current CrossFi networks are:

#### Testnet&#x20;

`crossfi-evm-testnet-1`.

#### Mainnet&#x20;

`crossfi-mainnet-1`.

***

### Explorers

#### Testnet Explorers&#x20;

* Block explorer - [https://scan.testnet.ms/](https://scan.testnet.ms/)
* Execution/Consensus layers explorer - [https://test.xfiscan.com/](https://test.xfiscan.com/)

#### Mainnet Explorers&#x20;

Execution/Consensus layers explorer - [https://xfiscan.com/](https://xfiscan.com/)

***

### Hardware

Running a full archive node can be resource intensive as the full current `crossfi-1` can be is over `1TB`. For those who wish to run state sync or use quicksync, the following hardware configuration is recommended:

<table data-full-width="false"><thead><tr><th>Node Type</th><th>RAM</th><th>Storage</th></tr></thead><tbody><tr><td>Validator</td><td>32GB</td><td>500GB-2TB*</td></tr><tr><td>Full</td><td>16GB</td><td>2TB</td></tr><tr><td>Default</td><td>16GB</td><td>1TB</td></tr></tbody></table>

\* Storage size for validators will depend on level of pruning.

***

### General Configuration

Make sure to walk through the basic setup and configuration. Operators will need to initialize `crossfid`, download the genesis file for `crossfi-1`, and set persistent peers and/or seeds for startup.

### Initialize Chain

#### Testnet&#x20;

{% code fullWidth="false" %}
```bash
wget https://github.com/crossfichain/crossfi-node/releases/download/v0.3.0-prebuild3/crossfi-node_0.3.0-prebuild3_linux_amd64.tar.gz && tar -xf crossfi-node_0.3.0-prebuild3_linux_amd64.tar.gz
git clone https://github.com/crossfichain/testnet.git
./bin/crossfid start --home ./testnet
```
{% endcode %}

#### Mainnet&#x20;

```bash
wget https://github.com/crossfichain/crossfi-node/releases/download/v0.3.0/crossfi-node_0.3.0_linux_amd64.tar.gz && tar -xf crossfi-node_0.3.0_linux_amd64.tar.gz
git clone https://github.com/crossfichain/mainnet.git
./bin/crossfid start --home ./mainnet
```



### Seeds & Peers

Upon startup the node will need to connect to peers. If there are specific nodes a node operator is interested in setting as seeds or as persistent peers, this can be configured in `~/.crossfid/config/config.toml`

{% code fullWidth="false" %}
```
# Comma separated list of seed nodes to connect to
seeds = "<seed node id 1>@<seed node address 1>:26656,<seed node id 2>@<seed node address 2>:26656"

# Comma separated list of nodes to keep persistent connections to
persistent_peers = "<node id 1>@<node address 1>:26656,<node id 2>@<node address 2>:26656"
```
{% endcode %}

### Pruning of State - Optional Step&#x20;

There are four strategies for pruning state. These strategies apply only to state and do not apply to block storage. A node operator may want to consider custom pruning if node storage is a concern or there is an interest in running an archive node.

To set pruning, adjust the `pruning` parameter in the `~/.crossfid/config/app.toml` file. The following pruning state settings are available:

1. `everything`: Prune all saved states other than the current state.
2. `nothing`: Save all states and delete nothing.
3. `default`: Save the last 100 states and the state of every 10,000th block.
4. `custom`: Specify pruning settings with the `pruning-keep-recent`, `pruning-keep-every`, and `pruning-interval` parameters.

By default, every node is in `default` mode which is the recommended setting for most environments. If a node operator wants to change their node's pruning strategy then this **must** be done before the node is initialized.

In `~/.crossfid/config/app.toml`

```
# default: the last 100 states are kept in addition to every 500th state; pruning at 10 block intervals
# nothing: all historic states will be saved, nothing will be deleted (i.e. archiving node)
# everything: all saved states will be deleted, storing only the current state; pruning at 10 block intervals
# custom: allow pruning options to be manually specified through 'pruning-keep-recent', 'pruning-keep-every', and 'pruning-interval'
pruning = "custom"

# These are applied if and only if the pruning strategy is custom.
pruning-keep-recent = "10"
pruning-keep-every = "1000"
pruning-interval = "10"
```

Passing a flag when starting `crossfid` will always override settings in the `app.toml` file. To change the node's pruning setting to `everything` mode then pass the `---pruning everything` flag when running `crossfid start`.

{% hint style="info" %}
If running the node with pruned state, it will not be possible to query the heights that are not in the node's store.
{% endhint %}

***

### REST API - Optional&#x20;

By default, the REST API is disabled. To enable the REST API, edit the `~/.crossfid/config/app.toml` file, and set `enable` to `true` in the `[api]` section.

```
###############################################################################
###                           API Configuration                             ###
###############################################################################
[api]
# Enable defines if the API server should be enabled.
enable = true
# Swagger defines if swagger documentation should automatically be registered.
swagger = false
# Address defines the API server to listen on.
address = "tcp://0.0.0.0:1317"
```

Optionally activate swagger by setting `swagger` to `true` or change the port of the REST API in the parameter `address`. After restarting the application, access the REST API on `<NODE IP>:1317`.

***

### GRPC - Optional&#x20;

By default, gRPC is enabled on port `9090`. The `~/.crossfid/config/app.toml` file is where changes can be made in the gRPC section. To disable the gRPC endpoint, set `enable` to `false`. To change the port, use the `address` parameter.

```
###############################################################################
###                           gRPC Configuration                            ###
###############################################################################
[grpc]
# Enable defines if the gRPC server should be enabled.
enable = true
# Address defines the gRPC server address to bind to.
address = "0.0.0.0:9090"
```

***

## Sync Options

There are three main ways to sync a node on the Crossfi Chain; Blocksync, State Sync, and Quicksync. See the matrix below for the Hub's recommended setup configuration. This guide will focus on syncing two types of common nodes; full and pruned. For further information on syncing to run a validator node, see the section on [Validators](becoming-a-validator/).

There are two types of concerns when deciding which sync option is right. _Data integrity_ refers to how reliable the data provided by a subset of network participants is. _Historical data_ refers to how robust and inclusive the chain’s history is.

|                          | Low Data Integrity  | High Data Integrity |
| ------------------------ | ------------------- | ------------------- |
| Minimal Historical Data  | Quicksync - Pruned  | State Sync          |
| Moderate Historical Data | Quicksync - Default |                     |
| Full Historical Data     | Quicksync - Archive | Blocksync           |

Make sure to consult the [hardware](join-a-network.md#hardware) section for guidance on the best configuration for the type of node operating.

***

### Blocksync

Blocksync is faster than traditional consensus and syncs the chain from genesis by downloading blocks and verifying against the merkle tree of validators. For more information see [Tendermint's Fastsync Docs](https://docs.tendermint.com/v0.34/tendermint-core/fast-sync.html)

When syncing via Blocksync, node operators will either need to manually upgrade the chain or set up [Cosmovisor](join-a-network.md#cosmovisor) to upgrade automatically.

It is possible to sync from previous versions of the Crossfi Chain. See the matrix below for the correct `crossfid` version. See the [testnet archive](https://github.com/cosmos/testnet) for historical genesis files.

| Chain Id                | Crossfi Version |
| ----------------------- | --------------- |
| `crossfi-evm-testnet-1` | `v0.2.0`        |

**Getting Started**

Start crossfid to begin syncing with the `skip-invariants` flag. For more information on this see [Verify ](join-a-network.md#verify-testnet)network.&#x20;

```bash
crossfid start --x-crisis-skip-assert-invariants
```

### State Sync

State Sync is an efficient and fast way to bootstrap a new node, and it works by replaying larger chunks of application state directly rather than replaying individual blocks or consensus rounds. For more information, see [Tendermint's State Sync docs](https://github.com/tendermint/tendermint/blob/v0.34.x/spec/p2p/messages/state-sync.md).

To enable state sync, visit an explorer to get a recent block height and corresponding hash. A node operator can choose any height/hash in the current bonding period, but as the recommended snapshot period is `1000` blocks, it is advised to choose something close to `current height - 1000`.

With the block height and hash selected, update the configuration in `~/.crossfid/config/config.toml` to set `enable = true`, and populate the `trust_height` and `trust_hash`. Node operators can configure the rpc servers to a preferred provider, but there must be at least two entries. It is important that these are two rpc servers the node operator trusts to verify component parts of the chain state. While not recommended, uniqueness is not currently enforced, so it is possible to duplicate the same server in the list and still sync successfully.

{% hint style="info" %}
In the future, the RPC server requirement will be deprecated as state sync is [moved to the p2p layer in Tendermint 0.38](https://github.com/tendermint/tendermint/issues/6491).
{% endhint %}

```bash
#######################################################
###         State Sync Configuration Options        ###
#######################################################
[statesync]
# State sync rapidly bootstraps a new node by discovering, fetching, and restoring a state machine
# snapshot from peers instead of fetching and replaying historical blocks. Requires some peers in
# the network to take and serve state machine snapshots. State sync is not attempted if the node
# has any local state (LastBlockHeight > 0). The node will have a truncated block history,
# starting from the height of the snapshot.
enable = true

# RPC servers (comma-separated) for light client verification of the synced state machine and
# retrieval of state data for node bootstrapping. Also needs a trusted height and corresponding
# header hash obtained from a trusted source, and a period during which validators can be trusted.
#
# For Cosmos SDK-based chains, trust_period should usually be about 2/3 of the unbonding time (~2
# weeks) during which they can be financially punished (slashed) for misbehavior.
rpc_servers = "" 
trust_height = 0
trust_hash = ""
trust_period = "168h0m0s"
```

Start crossfid to begin state sync. It may take take some time for the node to acquire a snapshot, but the command and output should look similar to the following:

```bash
$ crossfid start --x-crisis-skip-assert-invariants

...

> INF Discovered new snapshot format=1 hash="0x000..." height=8967000 module=statesync

...

> INF Fetching snapshot chunk chunk=4 format=1 height=8967000 module=statesync total=45
> INF Applied snapshot chunk to ABCI app chunk=0 format=1 height=8967000 module=statesync total=45
```

Once state sync successfully completes, the node will begin to process blocks normally. If state sync fails and the node operator encounters the following error: `State sync failed err="state sync aborted"`, either try restarting `crossfid` or running `crossfid unsafe-reset-all` (make sure to backup any configuration and history before doing this).

### Quicksync

Quicksync.io offers several daily snapshots of the Crossfi Chain with varying levels of pruning (`archive` 1.4TB, `default` 540GB, and `pruned` 265GB). For downloads and installation instructions, visit the [Cosmos Quicksync guide](https://quicksync.io/networks/cosmos.html).

***

## Snapshots

Saving and serving snapshots helps nodes rapidly join the network. Snapshots are now enabled by default effective `1/20/21`.

While not advised, if a node operator needs to customize this feature, it can be configured in `~/.crossfid/config/app.toml`. The Crossfi Chain recommends setting this value to match `pruning-keep-every` in `config.toml`.

{% hint style="info" %}
It is highly recommended that node operators use the same value for snapshot-interval in order to aid snapshot discovery. Discovery is easier when more nodes are serving the same snapshots.
{% endhint %}

In `app.toml`

```
###############################################################################
###                        State Sync Configuration                         ###
###############################################################################

# State sync snapshots allow other nodes to rapidly join the network without replaying historical
# blocks, instead downloading and applying a snapshot of the application state at a given height.
[state-sync]

# snapshot-interval specifies the block interval at which local state sync snapshots are
# taken (0 to disable). Must be a multiple of pruning-keep-every.
snapshot-interval = 1000

# snapshot-keep-recent specifies the number of recent snapshots to keep and serve (0 to keep all).
snapshot-keep-recent = 10
```

***

### Cosmovisor

Cosmovisor is a process manager developed to relieve node operators of having to manually intervene every time there is an upgrade. Cosmovisor monitors the governance module for upgrade proposals; it will take care of downloading the new binary, stopping the old one, switching to the new one, and restarting.

For more information on how to run a node via Cosmovisor, check out the [docs](https://github.com/cosmos/cosmos-sdk/blob/v0.45.0/cosmovisor/README.md).

## Running via Background Process

To run the node in a background process with automatic restarts, it's recommended to use a service manager like `systemd`. To set this up run the following:

```bash
sudo tee /etc/systemd/system/<service name>.service > /dev/null <<EOF  
[Unit]
Description=crossfid Daemon
After=network-online.target

[Service]
User=$USER
ExecStart=$(which crossfid) start
Restart=always
RestartSec=3
LimitNOFILE=4096

[Install]
WantedBy=multi-user.target
EOF
```

If using Cosmovisor then make sure to add the following:

```bash
Environment="DAEMON_HOME=$HOME/.crossfid"
Environment="DAEMON_NAME=crossfid"
Environment="DAEMON_ALLOW_DOWNLOAD_BINARIES=false"
Environment="DAEMON_RESTART_AFTER_UPGRADE=true"
```

After the `LimitNOFILE` line and replace `$(which crossfid)` with `$(which cosmovisor)`.

Run the following to setup the daemon:

```bash
sudo -S systemctl daemon-reload
sudo -S systemctl enable <service name>
```

Then start the process and confirm that it's running.

```bash
sudo -S systemctl start <service name>

sudo service <service name> status
```

***

### Exporting State

crossfid can dump the entire application state into a JSON file. This application state dump is useful for manual analysis and can also be used as the genesis file of a new network.

{% hint style="warning" %}
The node can't be running while exporting state, otherwise the operator can expect a `resource temporarily unavailable` error.
{% endhint %}

Export state with:

```bash
crossfid export > [filename].json
```

It is also possible to export state from a particular height (at the end of processing the block of that height):

```bash
crossfid export --height [height] > [filename].json
```

If planning to start a new network from the exported state, export with the `--for-zero-height` flag:

```bash
crossfid export --height [height] --for-zero-height > [filename].json
```

***

### Verify Network

Running invariants on each block is a best practice for disaster prevention. This ensures that the node operator maintains the correct and expect state of the network. &#x20;

Although this is important for the operation of a node, invariant checks are not enabled by defauls because they are computationally expensive. To run a node with these checks start your node with the assert-invariants-blockly flag:

```bash
crossfid start --assert-invariants-blockly
```

If an invariant is broken on the node, it will panic and prompt the operator to send a transaction which will halt the network. For example the provided message may look like:

```bash
invariant broken:
    loose token invariance:
        pool.NotBondedTokens: 100
        sum of account tokens: 101
    CRITICAL please submit the following transaction:
        crossfid tx crisis invariant-broken staking supply
```



