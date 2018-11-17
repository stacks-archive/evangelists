# Blockstack Evangelists

This repo is a collection of presentations and explainers for anyone presenting about Blockstack to technical audiences, as well as non-technical audiences. Also included are presentations that have been given at various conferences and events.

### Adding your slide deck

If you have been to an event lately, or are going to be at an event soon, we would love to see your slides and share that information so others can use it too!

To add your slide deck please open a Pull Request against the repository and add your your presentation with the file name format `{presentation_name}-{github_username}.pptx` (or other format) to the `/community-slides` folder. Also add a line to the [`README.md`](/community-slides/README.md) in that folder with the following format:

```md
- [{presentation_name}](/community-slides/{file_name}) - @{github_username} ({month} {year})

Example

- [Blockstack For Beginners](/community-slides/blockstack4beginners-dhealy05.pptx) - @dhealy-5 (December 2017)
```

### Requesting Content

To request some content for a Meetup you will be hosting, or to help clear up any things you are having trouble understanding, please open an issue on this repository with some details:

- I would like to see...
  * A description of what kind of content you would like to see
- This would help me...
  * An explanation of how this content would help you
- Resources for getting started...
  * Any current documentation or pages that exist on the topic. Search _at least_ this spot:
    * [All docs on Blockstack](https://docs.blockstack.org/)

### How Do I Become a World Class Blockstack Evangelist?

#### What is a Blockstack evangelist?
A Blockstack evangelist is:
 - Someone who is passionate about the Blockstack platform and ideals
 - Willing to share with fellow evangelists
 - Part product marketer, part developer/tinkerer, maybe both!

#### What are the product areas that I should learn to become a Blockstack expert?

The three pillars of the Blockstack Stack could be described as follows:

1. Decentralized Identity
2. Decentralized Storage [(Gaia)](https://github.com/blockstack/gaia)
3. Discovery/Replication [(Atlas)](https://docs.blockstack.org/core/atlas/overview.html)

([whitepaper link](https://blockstack.org/whitepaper.pdf))

Below are other areas of knowledge that will be helpful, with some component pieces identified. If there is more you would like to see below [please open an issue or PR](https://github.com/blockstack/evangelists/issues/new)!

**System Architecture** (note: this will be changing in coming releases)
1. Component Architecture ([forum link](https://forum.blockstack.org/t/component-architecture/1417)) & Blockstack layers ([whitepaper](https://blockstack.org/whitepaper.pdf))
2. Blockstack Core API ([api docs](https://core.blockstack.org/))
4. `blockstack-core` (runs the atlas network) vs `blockstack api` (provides a REST interface)
5. Virtualchain ([repo](https://github.com/blockstack/virtualchain/))
6. Blockstack Browser ([repo](http://github.com/blockstack/blockstack-browser/))
7. Gaia Hubs ([repo](https://github.com/blockstack/gaia/tree/master/hub))

**Decentralized Storage (Gaia)**
1. Basics - Storage Layers, basic file operations ([blockstack.js](http://blockstack.github.io/blockstack.js/))
2. Multi-Reader data access ([Open an issue/PR to add this!](https://github.com/blockstack/evangelists/issues/new))
4. Driver API ([repo](https://github.com/blockstack/gaia/tree/master/hub/src/server/drivers))
