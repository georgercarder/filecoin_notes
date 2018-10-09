### Proof of Replication

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


