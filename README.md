> [!NOTE] 
> Would you like to know more about my security services?
> [Check out my website](https://jcsec.io/)!
---

# Roadmap to CosmWasm Security/Auditing

The following is a list of interesting resources in case you want to start auditing [CosmWasm](https://cosmwasm.com/) smart contracts. I have not personally reviewed some of the resources, but those have been useful to others in the past and therefore worthy of mention. 

 The obvious recommendation looks like this:
 1. Blockchain and smart contracts basics
 2. Rust lang
 3. CosmWasm
 4. CosmWasm Security


:wave: Do not hesitate to drop me a line if you have any personal favorites that you think should be listed or if you think some of the current additions are not worthy of attention


### Blockchain and smart contracts basics

You first need to be familiar with the basic concepts of blockchain technologies and smart contracts in general. I came from Solidity and Ethereum auditing myself, so I'm not very sure which ones to recommend if you don't have any experience and don't want to get much into it… But I enjoyed [Mastering Ethereum](https://github.com/ethereumbook/ethereumbook) back in the day. 

:information_desk_person: You can probably find a lot of recommendations for this already :)


### Rust language

You don´t need a high level of Rust programming to start, which is quite challenging IMO, just to be able to clearly understand Rust code and create basic programs. 
> [!TIP] 
>  For any question that could come to your mind during this journey, [the Rust Book](https://doc.rust-lang.org/stable/book/) will most likely be your bible.

There are a lot of free basic courses out there, for example: [Udemy: Ultimate rust crash course](https://www.udemy.com/course/ultimate-rust-crash-course/) and its second part [Ultimate rust 2](https://www.udemy.com/course/ultimate-rust-2/)
 
:bulb: You can find easy code examples to follow or try to implement yourself at [Rust by Example](https://doc.rust-lang.org/rust-by-example/). There are a lot of additional sites with Rust exercises such as [Exercism's Rust path](https://exercism.org/tracks/rust)

:star: [I loved Rustlings](https://github.com/rust-lang/rustlings), as you get to learn Rust by actually fixing code snippets that you have to previously understand which is quite similar to auditing in a sense. 


I sometimes use [Rust Playground](https://play.rust-lang.org/) as a quick ready-to-go environment to test random stuff and behaviors.
   

### CosmWasm

At this point, you already have at least basic knowledge of blockchain techs, smart contracts, and Rust. It is about time to actually get into CosmWasm! There is a set of posts featured by Ethan Frey [(@ethanfrey)](https://github.com/ethanfrey) that are now outdated but could still give you a nice overview and comparison with other techs:
- [CosmWasm for Developers](https://blog.cosmos.network/cosmwasm-for-developers-7640ee38430f)
- [CosmWasm for CTOs 0](https://medium.com/cosmwasm/cosmwasm-for-ctos-f1ffa19cccb8), [I: the architecture](https://medium.com/cosmwasm/cosmwasm-for-ctos-i-the-architecture-59a3e52d9b9c), [II: advanced usage](https://medium.com/cosmwasm/cosmwasm-for-ctos-ii-advanced-usage-ee04ce95d1d0), [IV: native integrations](https://medium.com/cosmwasm/cosmwasm-for-ctos-iv-native-integrations-713140bf75fc)


:milky_way: As CosmWasm is a Cosmos SDK module that will run in Cosmos chains, you should familiarize yourself with how Cosmos works and some core concepts. You should at least read the following Cosmos documentation:
1. [Introduction section](https://docs.cosmos.network/v0.50/learn/intro/overview). Includes high-level overview, application-specific blockchains, blockchain architecture, and main components of the Cosmos SDK.
2. [Basics section](https://docs.cosmos.network/v0.50/learn/beginner/app-anatomy). Includes anatomy of a Cosmos SDK application, transaction lifecycle, query lifecycle, accounts, and gas and fees.

:point_right: NOW is when we start diving into CosmWasm itself. I would say just reading the [CosmWasm Book](https://book.cosmwasm.com/) cover to cover is a good starting point to get all the concepts before trying to develop your contracts. In addition, [this one resource](https://github.com/CosmWasm/cosmwasm/blob/main/SEMANTICS.md) has been helpful to me for quick references from time to time, some details are reflected on The Book but some others are not so clear to me there.

CosmWasm smart contract programming will be your next stop. You should be able to write easy CW smart contracts, [CW Template](https://github.com/CosmWasm/cw-template) is a nice resource to play around with a bit. You can find a list of resources below, some of the content will overlap so the idea is not to do all of them but but to give more options
1. [CosmWasm Academy](https://academy.cosmwasm.com/) <-- best maintained one at the time of writing
2. [CosmWasm zero to hero](https://github.com/Callum-A/cosmwasm-zero-to-hero)
3. [Area 52](https://area-52.io/)

:heavy_plus_sign: [CosmWasm Plus](https://github.com/CosmWasm/cw-plus) is a set of publicly available base contracts of common implementations following the idea of [OpenZeppelin](https://github.com/OpenZeppelin/openzeppelin-contracts). Going over some of the main ones and understanding their architecture and behavior is an excellent way to start testing your Smart Contract analysis game, your main skill as a future auditor.
- [CW20 fungible token](https://github.com/CosmWasm/cw-plus/blob/main/packages/cw20/README.md)
- [CW721 non-fungible token](https://github.com/CosmWasm/cw-nfts/blob/main/packages/cw721/README.md)
- [CW1 fixed multisig](https://github.com/CosmWasm/cw-plus/tree/main/contracts/cw3-fixed-multisig)

:100: In addition, you should get familiar with Smart Contract testing as you will craft your PoCs using these, check [Mastering CosmWasm Multi-Test](https://medium.com/obi-money/learn-cosmwasm-multi-test-easy-rust-smart-contract-apps-96818550ba3d) for a practical crash course on the topic. Further documentation on the most used libraries can be found at:
- [Module cosmwasm_std::testing](https://docs.rs/cosmwasm-std/latest/cosmwasm_std/testing/index.html)
- [Crate cw_multi_test](https://docs.rs/cw-multi-test/latest/cw_multi_test/), there is also a [chapter in the CW Book](https://book.cosmwasm.com/basics/multitest-intro.html)

Getting familiar with [IBC in CosmWasm](https://github.com/CosmWasm/cosmwasm/blob/main/IBC.md) is a good addition as it will become more and more common in CW contracts. Although not mandatory at this point as it is not a basic feature, you will have to go through this sooner or later.

There is an additional framework for building CosmWasm smart contracts, [the Sylvia Framework](https://medium.com/cosmwasm/the-sylvia-framework-release-b4ffbb74fe3d). I have only been asked to audit one of these a handful of times, but I would say it is getting community attention.


### CosmWasm security

Now you have all the prerequisites to get into the audit and security specifics of CosmWasm! If you come from Solidity auditing, the lack of resources here will surprise you compared to the overload of beginner security stuff for Sol/EVM out there.

:scroll: First of all, as you may expect, the [CosmWasm Security Spotlight posts](https://github.com/jcsec-security/cosmwasm-security-spotlight) and any future ones in my [Medium (@jcsec-audits)](https://medium.com/@jcsec-audits). Then DAO DAO's [CosmWasm security best practices](https://github.com/DA0-DA0/dao-contracts/wiki/CosmWasm-security-best-practices) have some interesting bits of info too.

:muscle: The next stop is practical examples:
1. [Oak's CosmWasm Security Dojo](https://github.com/oak-security/cosmwasm-security-dojo). In addition to the challenges themselves, you will find an `EXPLAINATION.md` on each dir giving you further details and concepts that are very useful.
2. [Oak Security CTF](https://github.com/oak-security/cosmwasm-ctf). CosmWasm CTF which me and Richie created for Awesomwasm 2023, is a nice overview of different security issues of CW contracts. Medium difficulty I would say.
3. [DeFiVulnLabsCosmWasm](https://github.com/punishell/DeFiVulnLabsCosmWasm)


There are not many more good resources out there, so it is time to start reading CosmWasm audit reports. This is the best way to get familiar with the kind of security issues that we auditors find during our security reviews.

There are three companies that I know of that have multiple public reports of CosmWasm audits:
1. [Oak Security](https://github.com/oak-security/audit-reports)
2. [SCV Security](https://github.com/SCV-Security/PublicReports/tree/main/CW)
3. [Halborn](https://github.com/HalbornSecurity/PublicReports/tree/master/CosmWasm%20Smart%20Contract%20Audits), although most of their reports are from the "Terra era"


#### Tooling

I don't use many tools, to be honest, just a bunch of VS Extensions and Notion for note-taking.
- [Rust analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)
- [Better TOML](https://marketplace.visualstudio.com/items?itemName=bungcip.better-toml)
- [Inline Bookmarks](https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-inline-bookmarks) - audit is just not the same without this one, MVP
- [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb) - Do you know you can debug rust unit tests for CW smart contracts? I may write a Medium post in the future
- [Coverage Gutters](https://marketplace.visualstudio.com/items?itemName=ryanluker.vscode-coverage-gutters) - easily displays test coverage from a `lcov` file
- [Line Note](https://marketplace.visualstudio.com/items?itemName=tkrkt.linenote) - I sometimes like to add 2/3 lines of additional info without breaking the total number of lines and not creating extensive one-line comments

:round_pushpin: Aside from these I use a bunch of my own scripts that I am turning into a standalone "printer" tool, will publish it soon. Keep an eye on my new repos!
