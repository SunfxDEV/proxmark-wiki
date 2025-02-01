# Types of backdoors
**GEN 1a - UID** - OG of backdoor cards. Responds to and shows backdoor commands. Can be detected when system tests if the card responds to backdoor commands.


***


**CUID**- The second gen of backdoor cards. Doesnt use commands, instead the UID block can be written to like any other block. Can be detected if the system tries to write to block 0 and succeeds.


***


**FUID**- This is a totally different card internally. Block 0 can be written to once and never again, which makes it almost undetectable.


***


**UFUID**- A kind of upgrade to "normal" FUID cards. You can write to block 0 as often as you want, but once you issue the lock command its permanently locked. Which also makes it almost undetectable. I dont really see the improvement of FUID, but whatever.
