
<section data-background="white">
![BlockStack](https://media.githubusercontent.com/media/blockstack/designs/master/logo/external/RGB/logo/blockstack-logo-vertical-bug%402x.png)
###### Jack Zampolin - Engineering Partner

---

<section data-background="#270f34">

## What Is Blockstack? ##


Note:
1) Blockstack is a new decentralized Internet where users own their data and apps run locally.

2) Blockstack is an open source development API for the bitcoin blockchain that enables identity, storage, and discovery.

---

<section data-background="#270f34">
## Architecture ##

<img src="https://blockstack.org/images/visuals/blockstack-architecture-diagram.svg" width="500">

Note:
1) Lowest layer is the blockchain which Blockstack uses to bootstrap trust in the network. Currently we run on BTC, but because of the implementation Blockstack can easily move to other blockchains. This is because of our Virtualchain technology.

2) With the Virtualchain we have built the Blockstack Naming system which is functionally similar to DNS

3) Using these names as a basis we built out the Storage, Discovery, and Identity applications on top.  

---

<section data-background="#270f34">
## BlockStack API ##

[Discovery](https://blockstack.org/whitepaper.pdf)

[Storage](https://github.com/blockstack/blockstack-core/blob/rc-0.14.2/docs/gaia.md)

[Identity](https://blockstack.org/posts/blockchain-identity)


Note:

1) Discovery (BNS)

  a) Works like DHT, but defintely not a DHT.  The Atlas peer network is _unstructured_, unlike DHTs, which makes it more resilient to individual edges in the peer graph failing.

  b) Each peer has a 100% replica of all the system's zone files, so all your routing lookups are locally-handled (no Dyn DNS-like DDoS attacks are possible)

  c) As long as the peer network graph is connected (doesn't matter how), every peer will eventually get 100% of the zone files.  

2) Identity (Blockchain ID)

  a) Based on the Blockstack Naming System, users peg their identities to domains e.g. `jackzampolin.id`.

3) Storage (Gaia)

  a) Turns existing storage providers into dumb datastores (privacy, encryption)

  b) Uses familiar filesystem concepts such as getFile, putFile, inodes

  c) Implemented in a simple Javascript API (`getFile()`, `putFile()`)

---

<section data-background="#270f34">
## Discovery - Blockstack Naming System ##

<img src="https://blockstack.org/images/visuals/blockstack-tx-diagram.png" width="500">


Note:

1) Discovery (BNS)

  a) Works like DHT, but defintely not a DHT.  The Atlas peer network is _unstructured_, unlike DHTs, which makes it more resilient to individual edges in the peer graph failing.

  b) Each peer has a 100% replica of all the system's zone files, so all your routing lookups are locally-handled (no Dyn DNS-like DDoS attacks are possible)

  c) As long as the peer network graph is connected (doesn't matter how), every peer will eventually get 100% of the zone files.  

---

<section data-background="#270f34">
## Identity - Blockchain ID ##

[Onename](https://onename.com)

[Blockchain ID](https://blockstack.org/posts/blockchain-identity)

Note:
1) Register id via the Blockstack browser or CLI.

2) .id namespace currently on bitcoin blockchain

3) Virtualchain makes this identity blockchain agnostic

---

<section data-background="#270f34">
## Virtualchain ##

[Whitepaper](https://blockstack.org/virtualchain_dccl16.pdf)

[Python Implementation](https://github.com/blockstack/virtualchain)

Note:

1) Virtualchain is a logical layer for multiplexing multiple fork-consistent state transition journals on a blockchain.

  a) Blockchains can fail (Namecoin)

  b) Betting on any one blockchain this early in the evolution of the space is a losing bet

  c) Application's journal can be forked and corrupted by the underlying blockchain

2) Used during namecoin -> bitcoin chain migration of BNS

---

<section data-background="#270f34">
## Storage - Gaia ##

<img src="https://raw.githubusercontent.com/blockstack/gaia/master/figures/gaia-getfile.png" width="500">

Note:

1) Using BNS users point their domain name to a storage backend.

2) Access is granted to applications through the identity system.

3) Storage backend currently Dropbox. Adding support for S3 compatible backends (AWS, Google, Azure, Minio)

---

## Find Us ##

* Slack - chat.blockstack.org
* Forum - forum.blockstack.org
* Twitter - @BlockstackOrg
* Github - github.com/blockstack/
* Meetup - meetup.com/Blockstack-Portland
