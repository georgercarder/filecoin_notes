### Proof of Replication

#### notes from study of 'Proof of Replication' technical report by Juan Benet, David Dalrymple, and Nicola Greco of Protocol Labs

P prover
V verifier
c challenge
pi^c proof

Properties:

**privately verifiable** A sceme is privately verifiable if V is a user with a secret verifying key generated during setup, or any other party shares that key with user. Useful in Cloud Computing settings.
For this paper PoS "Proofs of Storage" schemes are privately verifiable. 

**publicly verifiable** A scheme is publicly verifiable if V can be any party with access to public data (a verifying key) but no access to the oriinal data, or secret info generated during setup.
Useful in "DSN" Decentralized Storage Network settings where a verifier may be new participants who have access only to public data as context of previous proof scheme setups.

**transparent** A scheme is transparent if there is no extra info, sk, that enables P to generate a valid proof without having data D. i.e. cannot forge a proof of replication.
Necessary in Decentralized Storage Networks.

**retrievability** A scheme supports retrievability, if it is possible for V to extract and reconstruct D merely by issueing many challenges c to P and aggregating corresponding proofs pi^c, see PoRet.

**dynamic** A PoS scheme is dynamic if it enables the user V to dynamically update data D to D' stored at server P, to support mutable data without requiring a completely new setup. Dynamic PoS schemes are useful in Cloud Storage settings, and systems with large, frequently mutable data, without need for version history.

**non-outsourceable** A scheme is non-outsourceable if P cannot outsource her work to some other prover P' (storage, work, proof-generation) and convince V that P did the work. Non-outsourceable schemes are useful in Cloud computing, Cryptocurrencty, and Decentralized Storage Network settings, where P may be rewareded for providing space, and the users or V wish to ensure P is actually providing the service.

**authenticated** A scheme is authenticated if the identity of the prover can be verified during a proof verification. Example, a digital signature might be required as part of generating pi^c to prove identity pk_i.
Authentication can help make schemes non-outsourceable, since a prover would have to reveal secret key to others.

**time-bounded** A proving scheme is time-bounded if a proof is only valid during a span of time. i.e. proof must be calculated within timeframe else it is not valid.

**useful**  A scheme is useful if it can achieve separte useful work or useful storage as part of its operation or as a side effect. Example: storing and verifying a verifier-chosen D (PDP, PoRet, PoRep) is useful wherease storing and verifying a randomly-generated D (PoSpace) is not useful.

#### Kinds of proofs

Provable Data Possession (PDP) schemes allow user V to send data D to server P, and later V can repeatedly check whether P is still storing D.
Useful in Cloud storage or other outsourcing settings.
Can be either private or publicly verifiable, static or dynamic. Many schemes exist.

Proof of Retrievability (PoRet) similar to PDP but enable extracting D. Prevents P from holding D hostage, since V can reconstruct D from leaks from proofs.. --Shamir secrets..

Proof of Storage (Pos) schemes allow V to outsource storage of D to P and then repeatedly check if P is still storing D. PDPs and PoRets were independently introduced around 2007. Since then, the concept of Proofs of Storage generalizes PDP and PoRets. This paper is PoReps, a new type of Pos.

Proof of Replication (PoRep) scheme are another kind of Pos that additionally ensures that P is dedicating unique physical storage to storing D. P cannot pretend to store D twice and deduplicate the storage. Useful in Cloud Storage and DSN where ensuring proper level of replication is important, and where rational servers may create Sybil identities and sell their service twice ot the same user. PoRep schemes ensure each replica is stored independently. Some PoRep schemes may also be PoRet schemes.
Proof of Work (PoW) schemes allow prover P to convince verifier V that P has spent some resources. The original use case presents this scheme to allow a server V to ratelimit usage by asking user P to do some expensive work per-request.
