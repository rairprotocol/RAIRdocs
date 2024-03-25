# RAIR Open License Protocol (DRAFT)

*not final, tbd final tokenomics*

## Abstract
> The RAIR web3 infrastructure stack enables the creation of scalable Dapps through an open token licensing model. The RAIR open token license inherits the Apache 2.0 methodology by requiring a NFT license to be included inside the source License.md file. This allows for secure onchain tracking of licenses for the first time. 

Table of Contents
=================

- [ ]  [1. Introduction](#1-Introduction)
    - [ ] [History [1.1]](#History-11)
    - [ ] [State of Web3 [1.2]](#State-of-Web3-12)
    - [ ] [RAIR [1.3]](#RAIR-13)

- [ ]  [2. RAIR Open Source Codebase](#2-RAIR-Open-Source-Codebase)
    - [ ] [RAIRsolidity [2.1]](#RAIRsolidity-21)
    - [ ] [RAIRnode [2.2]](#RAIRnode-22)
    - [ ] [RAIRfrontend [2.3]](#RAIRfrontend-23)
    - [ ] [RAIRmedia [2.4]](#RAIRmedia-24)
    - [ ] [RAIRsync [2.5]](#RAIRsync-25)
    - [ ] [RAIRinfra [2.6]](#RAIRinfra-26)

- [ ]  [3. Open Token Licensing Model](#3-Open-Token-Licensing-Model)
    - [ ] [Licensing [3.1]](#Licensing-31)
    - [ ] [Permissive Licenses [3.2]](#Permissive-Licenses-32)
    - [ ] [Apache 2.0 [3.3]](#Apache-20-33)
    - [ ] [Risks and Benefits [3.4]](#Risks-and-Benefits-34)

- [ ]  [4. Tokenomics](#4-Tokenomics)

* [Acknowledgements](#Acknowledgements)
    * [References](#References)


  ----------------
 
## 1. Introduction
The business model of the internet hinges on the interplay of proprietary and open source. In the typical model, an enterprise develops an open source underlying codebase, that is then monetized by a centralized for profit corporation. 

### History [1.1]
Redhat Linux pioneered this model in the late 1990s, much to the chagrin of Linux core developers. Despite a valiant effort to reward Linux contributors with shares of stock in the Redhat corporation, the systems for compensating open source development remain controversial.[1](#References) 

In the web2 era, proprietary moats developed using the underlying rails of HTTP:// and other core protocols. While users rely on the open internet to access the FAANG behemoths, in web2 no monetization inherently accrues to the maintainers of the underlying protocols. 

### State of Web3 [1.2]
With the rise of public persistent data (aka blockchain) the monetization of open source entered a new "Web3" era. 

Developers believing in the protocol, for the first time could be compensated in the native unit of the protocol. Either by purchasing tokens directly, or through increasingly sophisticated grant mechanisms. By 2016, this thesis was codified into the seminal blog post "Fat Protocols [2](#References) where the author posits open source protocol tokens will solve the Redhat vs Linux compensation and incentive issue. 

Fast forward to 2024, and it is mandatory for the core protocol layers of Web3 (L1/L2 blockchains, Oracles, DA, Restaking, etc) to be open source to be trusted. //However// the Dapps built on top of Web3 are largely NOT. The VC model to fund teams that take open source infrastructure to then build proprietary business logic moats on top of is still alive and well.[3](#References)  Conjecture.. the development of Web3 killer Dapps is being stymied by this proprietary smothering.  

### RAIR [1.3]
The RAIR protocol has been in active development since 2019 as an investor backed enterprise SaaS product. In 2024, the entire RAIR Codebase is available for the first time via an open source Apache 2.0[4](#References) token licensing model.

Throughout this whitepaper, we will articulate our reasoning for going fully open source, and expound upon our token licensing model to reward the development of the RAIR token supported Dapp layer.  

----------------

## 2. RAIR Open Source Codebase
The RAIR codebase comprises 6 primary microservices that help Dapps deploy and scale. Used together or independently, this code base allows developers to build their own independent NFT marketplace and DRM infrastructure with all relevant smart contracting, account creation, and scalable offchain cloud management logic. 

All source code and a full explanation of functionality is available on the RAIRprotocol Github. github.com/rairprotocol

### RAIRsolidity [2.1]
Granular onchain NFT minting, royalty, resale, fungible token credit, and marketplace logic via ERC2535 upgradeable diamond multi-proxy contracts. Native EVM support for mainnet ETH, Astar, BSC, Matic + Testnets. Documentation for needed OpenZeppelin, Hardhat, etc deployment. Fully verified on Etherscan and relevant block explorers.

### RAIRnode [2.2]
Backend to create your own modular API endpoints and offchain infrastructure. Environment variables and full open source Docker image repository allows developers to quickly spin up their own backend infrastructure by inputting relevant paths and API keys. 

* Many critical out-of-the-box integrations can be deployed via API environment variables including: AA wallets, Yoti AI facial scanning, MongoDB Cloud Atlas, Hashicorp vault, Filebase. 

### RAIRfrontend [2.3]
Deploy customizable mobile first NFT marketplace frontends using modular REACT + Typescript framework. UIs to manage smart contract creation, user, DRM, metadata, UI/UX.

### RAIRmedia [2.4]
DRM protect content with a full FFmpeg encoder/transcoder. Store credentials to database or vault cluster. Store streaming data to IPFS or Cloud. 

### RAIRsync [2.5]
Specify all smart contract addresses to sync via Alchemy syncing engine. Supply Alchemy API key for native deployment. Extensible to other syncing infrastructure (Moralis et al).

### RAIRinfra [2.6]
Core to the RAIR value proposition is our full open sourcing of our cloud infrastructure tooling. While most projects stop at revealing the intricacies of their proprietary cloud setups, RAIR is committed to fully open sourcing all aspects of our knowledge base. This includes: Terraform scripts, CI/CD pipeline, Kubernetes configurations.

----------------

## 3. Open Token Licensing Model
RAIR is fully open sourcing 4 years and 2.5m USD+ of proprietary enterprise SaaS development. This means you can deploy, modify, and extend your own API endpoints on your own cloud. 
* RAIR C corp can assist with enterprise implementation on a SaaS/consulting basis. 
* RAIR DAO licenses all source code natively via soul-bound NFT tokens in exchange for burning RAIR tokens. 

### Licensing [3.1]
To review, software licenses come in 2 primary flavors: proprietary and permissive. Proprietary = copy our code and we can take legal action. Permissive = copy our code without the proper attribution, and we can take legal action.
### Permissive Licenses [3.2]
While not exhaustive, the following permissive licenses are the most widely used. Reasons will be given below for RAIR protocol NOT using the following licenses.
* MIT: Attribution is not rigorous enough as there is no public changelog requirement.
* BSD (Berkeley Software Distribution): Custom rules make this license too broad to perform standardized enforcement. 
* GPL (GNU Public License): Changelog requirement is good, though no requirement for inclusion of source License.md like Apache 2.0
* MPL (Mozilla Public License):  License contamination through the automatic inheritance of GPL prevents licensing by proprietary entities. 

### Apache 2.0 [3.3]
The Apache 2.0 license requires two critical components necessary for an NFT open licensing model.
* Public Changelog. If code is modified, publish the modifications publicly. 
* Inherited disclosure of license.Include the //***original***// License.md file into all derivative works. 

Taken together, these two properties form the basis for the RAIR protocol NFT license model. *E.g. Open source license is valid as long as a valid NFT exists inside of the license.md* 

### Risks and Benefits [3.4]
Benefits of this open source model include:
* Trust in fully transparent source code. No black boxes.
* Developer recognition and renumeration via token
* Increased development speed for all of Web3. No rebuilding wheels

The primary risk that prevents most Dapps from fully open sourcing their code base is the theft risk. Years and millions of dollars of IP can be forked without crediting the original creators. This risk is still present in an open token licensing model. The design of the token system must ensure the benefits of obtaining a license outweigh the costs both financial and reputational for stealing. 

----------------

### 4. Tokenomics

See dedicated tokenomics paper

----------------

## Acknowledgements 

The RAIR system is only possible thanks to years of hard work and dedication from our core development team. As RAIR transitions to a fully open source Dapp, these team members will be critical to steward the codebase into a prosperous future. 

@JuanMiguel
@SeanMichaels
@ChrisRose
@MashaMitkov
@ZephAlcala
@SureshArora
@Vino
@BrianBorg
@Valerii
@Kat
@Edprado
@Martincasado

----------------

## References

* [1] Stephen Shanklan. Late IPO change left many red-faced — cnet.com, 1 2002. https://www.
cnet.com/tech/tech-industry/late-ipo-change-left-many-red-faced/
* [2] Joel Monegro. Fat Protocols, 8 2016. https://www.usv.com/writing/2016/08/fat-protocols/
* [3] Alana Edgin. Texas Tech alum sells Tronic, Web3 innovator, for $12.25 billion, 3-2024. https://www.lubbockonline.com/story/business/2024/03/15/texas-tech-alum-sells-tronic-web3-innovator-for-12-25-billion/72971130007/
* [4] Apache Foundation. APACHE LICENSE, VERSION 2.0, 1 2004. https://www.apache.org/licenses/LICENSE-2.0
