# reconciled-manufacturing-ontology-serialisation
Common logic attachment to the paper "Manufacturing Resources, Capabilities, and Engineering Functions: Towards an Ontology-based Integration" for FOIS 2023

The .clif axioms were parsed with cltools: https://github.com/cmungall/cltools and macleod: https://github.com/thahmann/macleod.
In particular, a conversion of these axioms in tptp and prover9 format obtained with the macleod tool is also attached.

The .clif file does not import other .clif files, though some already exists that contain DOLCE primitives (e.g. those in the COLORE repository:  https://github.com/gruninger/colore). This is because such files contain a versione of DOLCE that is not aligned with most recent work. 

Macleod allows also for checking nontrivial consistency (if one also uses third parties theorem provers and/or model checkers). In our case Mace4 (https://www.cs.unm.edu/~mccune/prover9/) was able to find a nontrivial model. We report the corrisponding output in the .out file. 
The reproduction of this result will depend on the precise system configuration and installation of macleod, but, in our case, the command
```
check_consistency --nontrivial -f Downloads/macleod/paper-axioms.clif
```
correctly produced the .out file.
Unfortunately this is not enough to assert that the theory is consistent, because we would have to add also DOLCE axioms, but doing so would result in non-termination of the consistency check. 
