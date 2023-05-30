---
title: Installation
---

There are three primary methods of installing Bittensor on your local machine. 

# Installing from script. 

This is the most straightforward method and is recommended for the novice user as it will pre-install requirements, like Python, if they are not already present on your machine. Simply paste the following into your terminal: 

```bash dark
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/opentensor/bittensor/master/scripts/install.sh)"
```

---
# Installing with pip
```bash dark
pip3 install bittensor
```

---
# Installing from source
```bash dark
git clone https://github.com/opentensor/bittensor.git
$ python3 -m pip install -e bittensor/
```

Once installed, you can verify installation using the [Bittensor Command Line Interface](../reference/btcli) with ```btcli --help``` and/or check the installation in python.
```python numbered dark
import bittensor as bt
print( bt.__version__ )
```
