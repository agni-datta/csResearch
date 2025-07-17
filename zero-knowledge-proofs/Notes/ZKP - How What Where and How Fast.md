---
title: "ZKP: How, What, Where and How Fast?"
linter-yaml-title-alias: "ZKP: How, What, Where and How Fast?"
date created: Friday, January 17th 2025, 18:54:57
date modified: Thursday, July 17th 2025, 22:40:03
aliases: "ZKP: How, What, Where and How Fast?"
---

# ZKP: How, What, Where and How Fast?

## What is a zero-knowledge proof?

- [A New Approach To Protecting Secrets Is Discovered](https://www.nytimes.com/1987/02/17/science/a-new-approach-to-protecting-secrets-is-discovered.html) - The New York Times, February 17th, 1987
- [Zero Knowledge Proofs: An illustrated primer](https://blog.cryptographyengineering.com/2014/11/27/zero-knowledge-proofs-illustrated-primer/)
- [What are zk-SNARKs?](https://z.cash/technology/zksnarks.html)
- [“The Functionality of zk-SNARK”](http://qed-it.com/2017/07/challenge-one-the-functionality-of-zk-snark/) challenge set in [“The Hunting of the SNARK”](http://qed-it.com/2017/07/the-hunting-of-the-snark/).
- [“Probabilistic Proof Systems”](http://people.cs.georgetown.edu/jthaler/COSC544.html) course notes
- Vitalik Buterin’s introduction to SNARKs, part [1](https://medium.com/@VitalikButerin/quadratic-arithmetic-programs-from-zero-to-hero-f6d558cea649), [2](https://medium.com/@VitalikButerin/exploring-elliptic-curve-pairings-c73c1864e627), and [3](https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6); and STARKs, part [1](https://vitalik.ca/general/2017/11/09/starks_part_1.html), [2](https://vitalik.ca/general/2017/11/22/starks_part_2.html), and [3](https://vitalik.ca/general/2018/07/21/starks_part_3.html).

## History of Zero-knowledge proofs

- Invention of zero-knowledge
	- [Zero-Knowledge Proofs [GMR85]](http://groups.csail.mit.edu/cis/crypto/classes/6.876/papers/gmr-ZK.pdf)
	- [Non-Interactive ZK [BFM88]](https://dl.acm.org/citation.cfm?id=62222)
- Important landmarks for zk-SNARKs
	- [Succinct ZK[K92]](http://people.csail.mit.edu/vinodv/6892-Fall2013/efficientargs.pdf)
	- [Succinct Non-Interactive ZK [M94]](https://projecteuclid.org/download/pdf_1/euclid.lnl/1235415908)
	- [“SNARK” terminology and characterization of existence [BCCT11]](https://eprint.iacr.org/2011/443)
	- [Succinct NIZK without the PCP Theorem [Groth10]](http://www0.cs.ucl.ac.uk/staff/J.Groth/ShortNIZK.pdf)
	- Succinct NIZK without PCP Theorem & Quasi-linear prover time ([GGPR13](https://eprint.iacr.org/2012/215))

## Recent Zero-Knowledge proving systems

- [GGPR13](https://eprint.iacr.org/2012/215)
	- Pinocchio ([PGHR13](https://eprint.iacr.org/2013/279.pdf))
	- [BCGTV13](https://eprint.iacr.org/2013/507)
	- Geppetto ([CFHKKNPZ14](https://eprint.iacr.org/2014/976))
	- [BCTV14a](http://eprint.iacr.org/2013/879)
- [BCTV14b](https://eprint.iacr.org/2014/595)
	- Coda ([MS18](https://cdn.codaprotocol.com/static/coda-whitepaper-05-10-2018-0.pdf))
- [CTV15](https://eprint.iacr.org/2015/377)
- ZKBoo ([GMO16](https://eprint.iacr.org/2016/163.pdf))
- [Groth16](https://eprint.iacr.org/2016/260.pdf)
	- [GM17](https://eprint.iacr.org/2017/540.pdf)
	- [BG18](https://eprint.iacr.org/2018/187)
	- DIZK ([WZCPS18](https://eprint.iacr.org/2018/691))
		- Distributed implementation of [Groth16](https://eprint.iacr.org/2016/260.pdf)
		- Enables zkSNARK computations of up to billions of logical gates (100x larger than prior art) at a cost of 10μs per gate (100x faster than prior art)
		- Implements distributed polynomial evaluation/interpolation, distributed Lagrange polynomial computations, and distributed multi-scalar multiplication
- [BCCGP16](https://eprint.iacr.org/2016/263.pdf)
	- Bulletproofs ([BBBPWM17](https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf))
- Hybrid Interactive ZK ([CCM16](https://eprint.iacr.org/2016/583))
- ZKB++ / Picnic ([CDGORRSZ17](https://eprint.iacr.org/2017/279.pdf))
- Ligero ([AHIV17](https://acmccs.github.io/papers/p2087-amesA.pdf))
- Hyrax ([WTSTW17](https://eprint.iacr.org/2017/1132.pdf))
- zk-STARKs ([BBHR18](https://eprint.iacr.org/2018/046))
- Updatable Universal CRSs ([GKMMM18](https://eprint.iacr.org/2018/280))
	- Sonic ([MBKM19](https://eprint.iacr.org/2019/099))
- Hybrid NIZK ([ACM18](https://eprint.iacr.org/2018/557))
- Aurora ([BCRSVW18](https://eprint.iacr.org/2018/828.pdf))
- Libra ([XZZPS19](https://eprint.iacr.org/2019/317))

## Implementations of proving systems

|Name|Language|Curves|Proving systems|
|---|---|---|---|
|[libsnark](https://github.com/scipr-lab/libsnark)|C++|BN254|[Groth16](https://eprint.iacr.org/2016/260.pdf), [BCTV14a](http://eprint.iacr.org/2013/879), [BCTV14b](https://eprint.iacr.org/2014/595), [CTV15](https://eprint.iacr.org/2015/377)|
|[bellman](https://github.com/zkcrypto/bellman)|Rust|BLS12-381|[Groth16](https://eprint.iacr.org/2016/260.pdf)|
|[dalek bulletproofs](https://github.com/dalek-cryptography/bulletproofs)|Rust|ristretto255|[BBBPWM17](https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf)|
|[adjoint-io bulletproofs](https://github.com/adjoint-io/bulletproofs)|Haskell|secp256k1|[BBBPWM17](https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf)|
|[DIZK](https://github.com/scipr-lab/dizk)|Java|BN254|[Groth16](https://eprint.iacr.org/2016/260.pdf)|
|[snarkjs](https://github.com/iden3/snarkjs)|JavaScript|BN254|[Groth16](https://eprint.iacr.org/2016/260.pdf), [BCTV14a](http://eprint.iacr.org/2013/879)|
|[websnark](https://github.com/iden3/websnark)|WebAssembly|BN254|[Groth16](https://eprint.iacr.org/2016/260.pdf)|

Other implementations:

- [ZKBoo](https://github.com/Sobuno/ZKBoo)
- [ZKB++](https://github.com/IAIK/gzkbpp)
- [BBBPWM17](https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf)
	- [BulletProofLib](https://github.com/bbuenz/BulletProofLib) - Java implementation
	- [secp256k1-zkp (experimental)](https://github.com/ElementsProject/secp256k1-zkp/pull/16) - C implementation on secp256k1
- Picnic
	- [Reference implementation](https://github.com/Microsoft/Picnic)
	- [Optimized implementation](https://github.com/IAIK/Picnic)
- [emmy](https://github.com/xlab-si/emmy)
	- ZKP primitives for [Camenisch-Lysyanskaya anonymous credentials](https://eprint.iacr.org/2001/019.pdf)
	- Camenisch-Lysyanskaya anonymous credentials (work in progress)
	- client-server (prover-verifier) communication based on Protobuffers and gRPC
- [VC](https://archive.codeplex.com/?p=vc) implementation accompanying the Pinocchio ([PGHR13](https://eprint.iacr.org/2013/279.pdf)) and Geppetto ([CFHKKNPZ14](https://eprint.iacr.org/2014/976)) papers
- [ZEXE](https://github.com/scipr-lab/zexe) - a Rust library for decentralized private computation
	- [GM17](https://eprint.iacr.org/2017/540.pdf)
- [libSTARK](https://github.com/elibensasson/libSTARK) - Academic C++ library for zk-STARKs
	- [BBHR18](https://eprint.iacr.org/2018/046)
- [libiop](https://github.com/scipr-lab/libiop) - Academic C++ library for IOP-based zk-SNARKs.
	- [AHIV17](https://acmccs.github.io/papers/p2087-amesA.pdf)
	- [BCRSVW18](https://eprint.iacr.org/2018/828.pdf)

## Generating structured reference strings

Some proving systems require a structured reference string (SRS). The following works discuss secure SRS generation.

- [[BCGTV15]](https://ieeexplore.ieee.org/document/7163032/) - MPC for generating the SRS for [PGHR13](https://eprint.iacr.org/2013/279.pdf)/[BCGTV13](https://eprint.iacr.org/2013/507)
- [[BGG17]](https://eprint.iacr.org/2017/602) - improved MPC for generating the SRS for [PGHR13](https://eprint.iacr.org/2013/279.pdf)/[BCGTV13](https://eprint.iacr.org/2013/507)
- [[BGM18]](https://eprint.iacr.org/2017/1050) - “Powers of Tau” protocol for scalable generation of structured reference string for [Groth16](https://eprint.iacr.org/2016/260.pdf)

## Libraries for writing circuits

|Name|DSL|Host Language|Backed by|Description|
|---|---|---|---|---|
|[libsnark](https://github.com/scipr-lab/libsnark)’s gadgetlib1/2||C++|libsnark|Libraries for building circuits for preprocessing zk-SNARKs|
|[bellman](https://github.com/zkcrypto/bellman)||Rust|bellman|Library for building circuits; various gadgets in [sapling-crypto](https://github.com/zcash/librustzcash/tree/master/sapling-crypto/src/circuit)|
|[jsnark](https://github.com/akosba/jsnark)||Java|libsnark|Library for building circuits for preprocessing zk-SNARKs|
|[ZoKrates](https://github.com/JacobEberhardt/ZoKrates)|Python subset|Rust|libsnark, bellman|Toolbox for zk-SNARKs on Ethereum|
|[Snarky](https://github.com/o1-labs/snarky)|Embedded OCaml|OCaml|libsnark|Front-end for writing R1CS SNARKs|
|[Circom](https://github.com/iden3/circom)|Typed JS|JavaScript|snarkjs|Language for writing R1CS SNARKs|
|[Circomlib](https://github.com/iden3/circomlib)|Typed JS|JavaScript||Library of basic circuits for Circom|
|[ZEXE](https://github.com/scipr-lab/zexe)’s snark-gadgets||Rust|ZEXE|Module for building circuits, comes with pre-built algebra circuits|
|[ZkVM](https://github.com/interstellar/slingshot/tree/main/zkvm)||Rust|bulletproofs|Language for writing confidential smart contracts that create Bulletproofs R1CS proofs|

## General-purpose compilers from high-level languages

- [ZKPDL [MEKHL10]](https://www.usenix.org/legacy/event/sec10/tech/full_papers/Meiklejohn.pdf)
	- [Cashlib](https://github.com/brownie/cashlib) - C++ implementation
- Pinocchio ([PGHR13](https://eprint.iacr.org/2013/279.pdf))
	- [Pinocchio toolchain](https://archive.codeplex.com/?p=vc) - Python implementation
- [Pantry [BFRSBW13]](https://arifeldman.com/pub/pantry-sosp13.pdf)
- Geppetto ([CFHKKNPZ14](https://eprint.iacr.org/2014/976))
- TinyRAM ([BCGTV13](https://eprint.iacr.org/2013/507)), vnTinyRAM ([BCTV14a](http://eprint.iacr.org/2013/879)) and scalable TinyRAM ([BCTV14b](https://eprint.iacr.org/2014/595))
- [Buffet [WSRBW15]](https://cs.nyu.edu/~mwalfish/papers/buffet-ndss15.pdf)
- [C0C0 [KZMQCPPSS15]](https://eprint.iacr.org/2015/1093)
- [Pequin](https://github.com/pepper-project/pequin) - Toolchain to verifiably execute programs expressed in (a large subset of) C, backed by libsnark.
	- [Relevant publications](https://www.pepper-project.org/#publications)
- [Snårkl [SML17]](https://link.springer.com/chapter/10.1007%2F978-3-319-73305-0_3) - Haskell embedded DSL for verifiable computing
	- [Implementation backed by libsnark](https://github.com/gstew5/snarkl)
- [xJsnark [KPS18]](https://csdl.computer.org/csdl/proceedings/sp/2018/4353/00/435301a543.pdf)

## Example circuits

- [Zcash Sprout](https://github.com/zcash/zips/blob/master/protocol/protocol.pdf)
	- Based on [Zerocash [BCGGMTV14]](https://www.ieee-security.org/TC/SP2014/papers/Zerocash_c_DecentralizedAnonymousPaymentsfromBitcoin.pdf)
	- [C++ implementation over BN128 using libsnark](https://github.com/zcash/zcash/tree/master/src/zcash/circuit)
	- [Rust implementation over BLS12-381 using bellman](https://github.com/zcash-hackworks/sapling-crypto/tree/master/src/circuit/sprout)
- [ANONIZE [HMP15]](https://eprint.iacr.org/2015/681.pdf)
	- [Mobile applications (closed-source)](https://anonize.org/)
- [[KM18]](https://eprint.iacr.org/2018/176)
- [Zcash Sapling](https://github.com/zcash/zips/blob/master/protocol/sapling.pdf)
	- [Rust implementation over BLS12-381 using bellman](https://github.com/zcash-hackworks/sapling-crypto)
- [Zexe [BCGMMW2018]](https://eprint.iacr.org/2018/962.pdf)
- [Spacesuit](https://github.com/interstellar/slingshot/tree/main/spacesuit)
	- Rust implementation of the [Cloak](https://github.com/interstellar/slingshot/blob/main/spacesuit/spec.md) confidential assets protocol using Bulletproofs.

## Circuit optimization

- [Daira Hopwood’s notes from Zcon0](https://docs.google.com/document/d/1aZ1GUAJOBFuqD4GOo9HqAH8w4xJo7HM4Bjte5-wkdnU)

## Standardization efforts

- [Zero Knowledge Proof Standardization](https://zkproof.org/) and [1st Workshop](https://zkproof.org/standards_meetings.html)
- [Letter to NIST](https://zkp.science/docs/Letter-to-NIST-20160613-Advanced-Crypto.pdf) on standardizing new cryptographic standards
