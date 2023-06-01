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
