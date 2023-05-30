---
title: Introduction
---

Bittensor is a mining network, similar to Bitcoin, that rewards participants directly for their contributions in the form of compututational resources, expertise and innovation. The result is a robust informational ecosystem that offers censorship-resistant access to state-of-the-art artificial intelligence capabilities. The native currency, TAO, constitutes both reward and access token to the network. 

This documentation covers the three primary ways that users can interact with the network: mining, validating, and as a client. 

---
## [Clients](clients/clients)

Organizations and individuals seeking access to network competencies directly through client facing API's.  

```bash
In [4]: llm( "Heraclitus was a ?" )
Out[4]: 'Greek philosopher known for his doctrine of change and the famous quote, "No man ever steps in the same river twice."'
```

---
## [Miners](mining/mining)

Participants seeking to contribute computational resources and expertise in return for TAO. 

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

TAO holders who wish to participate in network governance and optimize their earnings in the ecosystem. 

```bash
bittensor/
    neurons/
        text_to_embedding/
        text_prompting/
            validators/
                core/
                    neuron.py
```
