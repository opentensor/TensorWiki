---
title: Introduction

---

Bittensor is a mining network, similar to Bitcoin, that offers censorship-resistant access to a decentralized network of machine learning models. By leveraging digital incentives and rewarding participants directly for their contributions of computational resources, expertise and innovation, Bittensor establishes a comprehensive, incentivized, and open-source ecosystem of artificial intelligence capabilities. The native currency, TAO, constitutes both reward and access token.

This documentation covers the three primary ways that users can interact with the network: mining, validating, and as a client. 

---
### Clients 

Users, researchers or companies, seeking to access bittensor directly using client facing APIs.

```bash
In [4]: llm( "Heraclitus was a ?" )
Out[4]: 'Greek philosopher known for his doctrine of change and the famous quote, "No man ever steps in the same river twice."'
```

---
### Miners

Individuals contributing compute, expertise or innovation into Bittensor and looking to get paid for it.

```bash
bittensor/
    neurons/
        text_prompting/
            miners/
                GPT4ALL/
                    neuron.py
```

---
### Validators

Tao holders looking to govern Bittensor directly and use the network at its full capactiy bandwidth and fidelity.

```bash
bittensor/
    neurons/
        text_to_embedding/
        text_prompting/
            validators/
                core/
                    neuron.py
```
