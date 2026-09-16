# dune-otter
A repository containing the extensions to LSTS DUNE for the NTNU Fish Otter

## Compatible DUNE version
This overlay is tested against the following upstream DUNE commit:
- Repo: https://github.com/LSTS/dune
- Commit: `f3b47e7b2` (master, version 2026.01.0)
- Branch used in our clone: `dune-2026-upgrade` (tracking origin/master at that commit)

The overlay is built on a plain clone of the official LSTS/dune repo. The
regenerated IMC files (`src/DUNE/IMC/*`) are build outputs and are intentionally
kept pristine in the DUNE clone; they are regenerated at build time from the
custom IMC fork (see below).

## Compatible IMC fork
The IMC message set must be the NTNU Otter fork:
- Repo: https://github.com/Fjord-Autonomy-Lab/imc
- Branch: `ntnuOtterASV` (based on LSTS/imc master 5.4.31, commit `72eafe7`)
- Configure DUNE with:
  `cmake -DIMC_URL=https://github.com/Fjord-Autonomy-Lab/imc/ -DIMC_TAG=ntnuOtterASV`

Note: the Otter custom messages were renumbered relative to the old
`nikkone/imc@ntnuOtterASV` branch (otterFormation 2010->2019, EstimatedFreq
911->910, Svec_value 2016->2020). DUNE and Neptus must both be built from the
same IMC fork.

## Use
First clone http://github.com/LSTS/dune.git
Enter the DUNE folder
Clone this library to a folder named user
Update the IMC version of DUNE to the Otter version (see above)
Warning: For updating IMC, python needs to be installed, and usable through the python command. In ununtu 20.04+, python3 is default, so sudo apt install python-is-python3
needs to be installed. After that, the descriptions on the LSTS/dune wiki can be followed. 
