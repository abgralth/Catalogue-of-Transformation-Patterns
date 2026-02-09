# Catalogue of Transformation Patterns

A **Transformation Pattern** (TP) is a formalism used in database transformation 
to guarantee that no information gets lost in the process.
Their purpose is to capture a particular type of transformation templates commonly found in various 
sectors of database theory, ranging from data integration and data normalisation to data cleaning and beyond.

Composed of a triple <DPS, DPT, M> with DPS and DPT denoting the state of a database schema 
before and after the application of a transformation written as a set of mappings M.

Those states, written as First-Order Schema (FOS), and the mappings written using the relational calculus notation
can notably be written in first-order logic. As such, the proof that a given pattern is lossless stems from a basic 
proof of mutual entailment. If we can prove the mutual entailment of (DPS U MS->T) === (DPT U MT->S) using any 
first-order logic prover, then we can show that the given pair of mappings ensures the information capacity preservation.

To do so, we use Prover9 as our theorem prover of choice https://www.cs.unm.edu/~mccune/mace4/

This directory contains three main folders: 
    - lossless TPs
    - lossy TPs
    - thesis' TPs

As of right now, only the third folder is non-empty.
It currently contains a FOL translation of every TPs presented in my thesis, as well as a couple more files related
to the propagation of constraints. Those serves to solidify the propagation rules we proposed by showing that, under most 
forms, precised by the rules themselves, the propagation of each constraint supported by our grammar is possible.
Each of those pattern verify the following assertion: Cs U Cl U Ms->t |= Cl', with Cl and Cl denoting the leftover constraints in 
S and T, respectively.
