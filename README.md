# mctdh_example_calculation
example calculation for spectra and state populations using MCTDH package

The common step for both spectra and state populations is to run propagation calculation that
generate time-auto-correlation function (auto file), time-dependent wavefunction fil(psi file) and potential energy surface(pes file).

To conduct propagation calculation. Three files are required:
1. Operator file (.op) specify the parameters for the vibronic model
2. Input file (.inp) specify the type of the calculation and basis set settings.
3. Bash file (.sh) the file that could be submitted to the cluster

To submit jobs to the cluster run command
sbatch submit_mctdh.sh [output_dir]

spectra can be generated using autospec84. It takes auto file as input files.
The command to generate spectra is
autospec84 -f [auto file name]

adiabatic / diabatic state population can be generated using adpop84. It takes psi and pes as input files  
The command to generate state population is
adpop84 -f [psi file name] -w -q (or -mc)

Thanks for Neil Raymond for providing me template mctdh input and operator files

