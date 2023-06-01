---
title: Delegation
---
Delegation is transferring Tao to a hotkey that is not owned by your coldkey. Hotkeys which have nominated themselves are open to recieve these delegations as a way of pool that investment from others. Often used to raise funds for a validator position or advertise a community project.

### How does delegation work?

All of the TAO delegated to a hotkey is available to be used within Bittensor's consensus mechanism. This gives the owning hotkey weight in the network to perform validation and thus recieve `dividends`. These dividends are distributed between the owning hotkey and the accounts that have nominated TAO. The chain currently enforces an `18%` cut for the owning hotkey while the remaining funds are distributed based on their proportion stake. 

!> Delegation Cut
The delegation cut is presently a hard coded but subject to change as the network evolves.

### Viewing Available Delegates
Hotkeys only become available for delegation once they have `nominated` themselves. To see a list of nominated validators you can run `btcli list_delegates`
```bash dark 
$ btcli list_delegates
```
![List Delegates](/images/list_delegates.png 'Output of List Delegates')

| Column | Description                                                 |
| :------ | ------------------------------------------------------------|
| INDEX   | Delegates with more total stake show higher in the list. |
| DELEGATE | The name of the delegate + clickable URL connected to delegate website. Only shows if the deleagate has registered. |
| SS58    | Clipped ss58 hotkey of the delegate.                       |
| NOMINATORS    | The number of unique coldkeys who have nominated to this hotkey.                       |
| DELEGATE STAKE(τ)    | The amount of stake the owning coldkey has delegates to this hotkey (distinct from TAO delegated from others).                       |
| TOTAL STAKE(τ)    | The total amount of stake delegated to this hotkey.                       |
| CHANGE/(4h)     | The percent difference between the total stake delegated with 4hours.                       |
| SUBNETS    | List of subnets this validator is registered on.                      |
| VPERMIT    | Shows "*" is the delegate has validator permit on each subnet ordered  SUBNETS                     |
| NOMINATOR/(24h)/kτ    | Stake cut taken by nominators to this delegate per 1000 TAO per day. |
| DELEGATE/(24h)    | Stake cut taken by the delegate within a 24 hour period.                        |
| Desc    | Delegate defined description.                     |


### Delegating TAO
You delegate TAO using btcli. This will show a list of delegates sorted by stake on your terminal. Read this list to find your delegate and use the index to select which to send stake to.
```bash dark 
$ btcli delegate
```

### Showing My Delegations
To show all your previously made delegations run `btcli my_delegates`, use `--all` to show delegations across all wallets.
```bash dark 
$ btcli my_delegates
```

### Becoming a delegate
You can `nominate` your hotkey to become and active delegate by running `btcli nominate`.
> You can [sign](../delegation/signing) your delegate information to give the hotkey a recognizable name an description.
```bash dark
$ btcli nominate
    --wallet.name YOUR_WALLET_NAME
    --wallet.hotkye YOUR_HOTKEY_NAME
```

## Further Reading
Delegation allows users to participate in Bittensor’s consensus mechanis without much TAO. By delegating Tao to a Validator, users are able to earn back Tao proportional to their contribution. Users are incentivized to delegate to a Validator based on the project that Validator is proposing. For example, a Validator can propose to validate and research image-to-text models. Users interested in image-to-text models on the Bittensor protocol are then encouraged to delegate Tao to that Validator to fund it with Tao. Hence, delegation is effectively a funding mechanism for projects on top of Bittensor.

By default, the delegates collect an 18\% share of all emissions from delegated TAO. The delegate validators must perform better than their peers to remain competitive while promoting growth and quality in the network. Delegation facilitates resource utilization, creating more powerful nodes and enhancing the network's innovative potential.

When delegating, users stake their Tao to a Hotkey belonging to a third-party Validator on the Bittensor network. This removes the need for users to provision their own hardware and deploy their own Validator. Instead, the delegating Hotkey will be responsible for validation and will provide any bond-emissions returns to the staking user's Coldkey, minus the 18\% fee. 

---
# Signing Delegates
---

Signing your delegate name, URL and description makes it show when others run btcli list_delegates. To do this you need to submit a pull request to the bittensor-delegates repo. 

1. Generating your details
```bash dark title=bittensor/scripts/validator_info_signature/generate.py link=https://github.com/opentensor/bittensor/scripts/validator_info_signature/generate.py
$ python3 generate.py
The mnemonic of your validator's Hotkey ( see file: ~/.bittensor/wallets/<coldkey>/hotkeys/<validator> ): ...
Your validator's descriptive name (i.e. Opentensor Foundation): ...
Your validator url (i.e. www.opentensor.org ): ...
A short description for your validator ( i.e. Build, maintain and advance Bittensor): ...
```

2. Verify a validator info signature.
```bash dark title=bittensor/scripts/validator_info_signature/verify.py link=https://github.com/opentensor/bittensor/scripts/validator_info_signature/verify.py
$ python3 verify.py
Validator information: sdasdasd
Validator signature: asdasdas
```

3. Submit a PR.
Visit this [bittensor repo](https://github.com/opentensor/bittensor) from here click `pull requests'. ...


