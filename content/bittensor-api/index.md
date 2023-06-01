<Accordion title="Subtensor">
---
title: bt.subtensor
---
# Subtensor Class Reference Documentation

---
## Introduction

The `Subtensor` is utilized for managing interactions with the subtensor chain. It serves as an interface to communicate with "Finney", Bittensor's main blockchain network, or others, enabling operations like querying and transacting.

## Examples

```python dark
# Creating a default chain connection to remote finney instance.
sub = bt.subtensor()

# Parsing --subtensor.network and --subtensor.chain_endpoint from the command line
sub = bt.subtensor( config = bt.subtensor.config() )

# Connecting subtensor's default local entrypoint "ws://127.0.0.1:9944"
sub = bt.subtensor( network = 'local' )

# Connecting to a specific endpoint
sub = bt.subtensor( chain_endpoint = "ws://127.0.0.1:9944" )
```
</Accordion>








<Accordion title="Methods">
## Methods

---
### nominate
```python
nominate(self, wallet: 'bittensor.Wallet', wait_for_finalization: bool = False, wait_for_inclusion: bool = True) -> bool
```
Designates the wallet's hotkey as a delegate.

---
### delegate
```python
delegate(self, wallet: 'bittensor.wallet', delegate_ss58: Optional[str] = None, amount: Union[Balance, float] = None, wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Adds a specific amount of stake to a delegate using a wallet.

---
### undelegate
```python
undelegate(self, wallet: 'bittensor.wallet', delegate_ss58: Optional[str] = None, amount: Union[Balance, float] = None, wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Removes a specific amount of stake from a delegate using a wallet.

---
### set_weights
```python
set_weights(self, wallet: 'bittensor.wallet', netuid: int, uids: Union[torch.LongTensor, list], weights: Union[torch.FloatTensor, list], version_key: int = bittensor.__version_as_int__, wait_for_inclusion:bool = False, wait_for_finalization:bool = False, prompt:bool = False) -> bool
```
Sets weights for a given netuid.

---
### register
```python
register(self, wallet: 'bittensor.Wallet', netuid: int, wait_for_inclusion: bool = False, wait_for_finalization: bool = True, prompt: bool = False, max_allowed_attempts: int = 3, output_in_place: bool = True, cuda: bool = False, dev_id: Union[List[int], int] = 0, TPB: int = 256, num_processes: Optional[int] = None, update_interval: Optional[int] = None, log_verbose: bool = False) -> bool
```
Registers the wallet to the chain.

---
### burned_register
```python
burned_register(self, wallet: 'bittensor.Wallet', netuid: int, wait_for_inclusion: bool = False, wait_for_finalization: bool = True, prompt: bool = False) -> bool
```
Registers the wallet to the chain by recycling TAO.

---
### transfer
```python
transfer(self, wallet: 'bittensor.wallet', dest: str, amount: Union[Balance, float], wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Transfers funds from the wallet to a destination public key address.

---
### get_existential_deposit
```python
get_existential_deposit(self, block: Optional[int] = None) -> Optional[Balance]
```
Returns the existential deposit for the chain.

---
### serve
```python
serve(self, wallet: 'bittensor.wallet', ip: str, port: int, protocol: int, netuid: int, placeholder1: int = 0, placeholder2: int = 0, wait_for_inclusion: bool = False, wait_for_finalization = True, prompt: bool = False) -> bool
```
Starts serving on a specific IP, port and protocol for a given netuid.

---
### serve_axon
```python
serve_axon(self, netuid: int, axon: 'bittensor.Axon', use_upnpc: bool = False, wait_for_inclusion: bool = False, wait_for_finalization: bool = True, prompt: bool

 = False) -> bool
```
Starts serving an Axon for a given netuid.

---
### serve_prometheus
```python
serve_prometheus(self, wallet: 'bittensor.wallet', port: int, netuid: int, wait_for_inclusion: bool = False, wait_for_finalization: bool = True) -> bool
```
Starts serving a Prometheus server on a specific port for a given netuid.

---
### add_stake
```python
add_stake(self, wallet: 'bittensor.wallet', hotkey_ss58: Optional[str] = None, amount: Union[Balance, float] = None, wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Adds a specific amount of stake to a hotkey uid.

---
### add_stake_multiple
```python
add_stake_multiple(self, wallet: 'bittensor.wallet', hotkey_ss58s: List[str], amounts: List[Union[Balance, float]] = None, wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Adds stake to each hotkey in the list from a common coldkey.

---
### unstake
```python
unstake(self, wallet: 'bittensor.wallet', hotkey_ss58: Optional[str] = None, amount: Union[Balance, float] = None, wait_for_inclusion:bool = True, wait_for_finalization:bool = False, prompt: bool = False) -> bool
```
Removes stake into the wallet coldkey from the specified hotkey uid.

---
### unstake_multiple
```python
unstake_multiple(self, wallet: 'bittensor.wallet', hotkey_ss58s: List[str], amounts: List[Union[Balance, float]] = None, wait_for_inclusion: bool = True, wait_for_finalization: bool = False, prompt: bool = False) -> bool
```
Removes stake from each hotkey in the list to a common coldkey.

</Accordion>



<Accordion title="Hyperparameters">

### rho
```python
rho (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network Rho hyperparameter if the network exists. Accepts an integer `netuid` representing the unique network ID and an optional integer `block` representing the block number.

---
### kappa
```python
kappa (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network Kappa hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### difficulty
```python
difficulty (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network Difficulty hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### burn
```python
burn (self, netuid: int, block: Optional[int] = None ) -> Optional[bittensor.Balance]
```
Returns the network Burn hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### immunity_period
```python
immunity_period (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network ImmunityPeriod hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_batch_size
```python
validator_batch_size (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network ValidatorBatchSize hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_prune_len
```python
validator_prune_len (self, netuid: int, block: Optional[int] = None ) -> int
```
Returns the network ValidatorPruneLen hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

### validator_logits_divergence
```python
validator_logits_divergence (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network ValidatorLogitsDivergence hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_sequence_length
```python
validator_sequence_length (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network ValidatorSequenceLength hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_epochs_per_reset
```python
validator_epochs_per_reset (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network ValidatorEpochsPerReset hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_epoch_length
```python
validator_epoch_length (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network ValidatorEpochLen hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### validator_exclude_quantile
```python
validator_exclude_quantile (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network ValidatorExcludeQuantile hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### max_allowed_validators
```python
max_allowed_validators(self, netuid: int, block: Optional[int] = None) -> Optional[int]
```
Returns the network MaxAllowedValidators hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### min_allowed_weights
```python
min_allowed_weights (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network MinAllowedWeights hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### max_weight_limit
```python
max_weight_limit (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network MaxWeightsLimit hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### scaling_law_power
```python
scaling_law_power (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network ScalingLawPower hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### synergy_scaling_law_power
```python
synergy_scaling_law_power (self, netuid: int, block: Optional[int] = None ) -> Optional[float]
```
Returns the network SynergyScalingLawPower hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### subnetwork_n
```python
subnetwork_n (self, netuid: int, block: Optional[int] = None ) -> int
```
Returns the network SubnetworkN hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### max_n
```python
max_n (self, netuid: int, block: Optional[int] = None ) -> Optional[int]
```
Returns the network MaxAllowedUids hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### blocks_since_epoch
```python
blocks_since_epoch (self, netuid: int, block: Optional[int] = None) -> int
```
Returns the network BlocksSinceLastStep hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

---
### tempo
```python
tempo (self, netuid: int, block: Optional[int] = None) -> int
```
Returns the network Tempo hyperparameter if the network exists. Inputs are `netuid` and an optional `block` number.

</Accordion>



