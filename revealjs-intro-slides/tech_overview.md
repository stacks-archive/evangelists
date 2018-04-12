
<section data-background="white">
![BlockStack](https://media.githubusercontent.com/media/blockstack/designs/master/logo/external/RGB/logo/blockstack-logo-vertical-bug%402x.png)
###### Aaron Blankstein

---

<section data-background="#270f34">
## What is Blockstack? ##

Blockstack is a new decentralized Internet

An app platform built with blockchain technology
Note:
1) Blockstack is a new decentralized Internet where users own their data and apps run locally.

2) Blockstack is an open source development API for the bitcoin blockchain that enables identity, storage, and discovery.

---

<section data-background="#270f34">
## Systems Architecture ##

Blockstack is composed of three systems

1. Blockchain Naming System
2. Atlas Network
3. Gaia Storage System

---

<section data-background="#270f34">
## Naming Systems ##

* Names important to:
  1. Computation
  2. Networks
  3. Practical Applications
* Apps _require_ names to identify users
* Centralized apps id users by names controlled centrally

---

<section data-background="#270f34">
## Decentralized Naming ##

* Who owns a name?
  * Associate name with a public key
* But how do you sort out contention?
  * Use a blockchain to determine ownership
* Now we need a blockchain!
  * Operations like registration, transfering, etc.

---

<section data-background="#270f34">
## Implementing our Blockchain ##

Key Idea:

Use a strong base-layer to implement our blockchain

Translate our operations into the bitcoin protocol

Let Bitcoin solve the problem of _ordering_ operations

---

<section data-background="#270f34">
## Virtual Chain ##

Pack our data into an `OP_RETURN`

Require name payments to be made in BTC

Require name owners be 1st TX input

Example: [TX](https://blockchain.info/tx/72bba213633b8c229207522ec39edf609d1dfe3a9c1d5336ad8604624d24bdb3)
```
Output Scripts
RETURN PUSHDATA(16)[69643a626c616e6b737465696e2e6964]
(decoded) id:blankstein.id
```

`blockstackd` nodes read BTC chain, validate blockstack operations

---

<section data-background="#270f34">
## Answering WHOIS ##

```
$ blockstack whois blankstein.id
{
    ...
  "owner_address": "15GAGiT2j2F1EzZrvjk3B8vBCfwVEzQaZx",
    ...
  "zonefile_hash": "f73d5a4ce030f76618dec839404fd1b793c5f015"
}
```

What do we do with this?

How do we associate a name with data?

---

<section data-background="#270f34">
## Obtaining Zonefiles ##

Use the Atlas network to translate `zonefile_hash` into zonefile data

```
$ blockstack get_name_zonefile blankstein.id
$ORIGIN blankstein.id
$TTL 3600
_http._tcp URI "https://gaia.blockstack.org/.../profile.json"
```

Atlas network is a gossip-replicated pool of decentralized network participants.

---


<section data-background="#270f34">
## Resolving a Profile ##

Translate a username into a user profile.
1. Obtain the zonefile
2. Read the linked profile
3. Validate with owner's public key

---


<section data-background="#270f34">
## Resolving a Profile ##

```
$ blockstack lookup blankstein.id
{
  "profile": {
    "@context": "http://schema.org",
    "@type": "Person",
    "account": [
      { ... }
    ]
  }
}
```


Example: [blankstein.id](https://explorer.blockstack.org/name/blankstein.id)

---


<section data-background="#270f34">
## Apps on Blockstack ##

* Users own names: determine by blockchain
* Names become data: Atlas network

Apps use that data to bootstrap pointers to other data, validate that data with public keys

Gaia Storage system, `blockstack.js`

---
