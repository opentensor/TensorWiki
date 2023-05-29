---
title: Installation
---
There are three primary ways to install Bittensor on your local machine: 

#### Installing from script. 
This is the easiest method and is recommended if you are new to coding as it will pre-install the requirements like python if they are not already present on your machine. To run the installer, simply paste the following into your terminal.
```bash dark
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/opentensor/bittensor/master/scripts/install.sh)"
```

---
#### Installing with pip
```bash dark
pip3 install bittensor
```

---
#### Installing from source
```bash dark
git clone https://github.com/opentensor/bittensor.git
$ python3 -m pip install -e bittensor/
```

Once installed, you can verify your installation using the [Bittensor Command Line Interface](../reference/btcli) with ```btcli --help``` and/or check the installation in python.
```python numbered dark
import bittensor as bt
print( bt.__version__ )
```