# Week 0 Assignment – Foundations of Blockchain & Cryptography

**Name:** ARYAN V NAIR  
**Roll No:** 25095014   
**Year:**  2  



## Assignment 1 – What is Hashing?

A hash function takes any input a word, a file, a whole document and converts it into a fixed-length string of characters. Something like:


a591a6d40bf420404a011733cfb7b190d62c65bf0bcda32b57b277d9ad9f146e


Three things make it useful:

**It's consistent.** Same input always gives the same output. No randomness.

**It's one-way.** You can't reverse-engineer the original data from the hash. You can share a hash freely without exposing what's inside.

**Tiny change, completely different output.** Change even one character in the input and the hash looks nothing like the original. This is what makes tampering detectable.

A good way to think about it — it's like a fingerprint for data. Two different people won't have the same fingerprint, and you can't reconstruct a person just from their fingerprint. Same idea.

In a blockchain, each block contains the hash of the previous block. So if someone tries to alter an old transaction, that block's hash changes — which breaks its link to the next block, and the one after that, all the way down. The chain makes tampering obvious.



## Assignment 2 – The Ripple Effect

*[Anders Brownworth's Blockchain Demo](https://andersbrownworth.com/blockchain/blockchain)*

I edited the data in Block #2. The moment I did, Block #2 turned red — its hash had changed. Then Block #3 went red because the "previous hash" it was holding no longer matched Block #2's new hash. Block #4 and #5 followed for the same reason.

Block #1 stayed valid since it was untouched.

| Block | Status |
|-------|--------|
| Block 1 |  Valid |
| Block 2 |  Invalid – data changed, hash changed |
| Block 3 |  Invalid – previous hash mismatch |
| Block 4 |  Invalid – previous hash mismatch |
| Block 5 |  Invalid – previous hash mismatch |

Each block's hash is derived from its own data plus the previous block's hash. Change one, and everything after it is broken. To actually get away with it on a real network, you'd have to re-mine every block after the edited one — faster than the rest of the network keeps adding new ones. That's what makes the blockchain practically tamper-proof.




