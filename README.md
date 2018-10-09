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
