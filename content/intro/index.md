---
title: Introduction
---
Bittensor is a mining network, similar to Bitcoin, that includes built-in incentives designed to encourage computers to provide access to machine learning models in an efficient and censorship-resistant manner, for instance; generating text, audio, and images, or for extracting numerical representations of these input types a.k.a embeddings.

There are three primary ways to interact with Bittensor which this documentation covers.

---
## [Clients](clients/clients)
Users, researchers or companies, seeking to access bittensor directly using client facing APIs.

```bash
In [4]: llm( "Heraclitus was a ?" )
Out[4]: 'Greek philosopher known for his doctrine of change and the famous quote, "No man ever steps in the same river twice."'
```

---
## [Miners](mining/mining)
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
## [Validators](validating/validating)
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
