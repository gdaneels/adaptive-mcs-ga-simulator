# adaptive-mcs-ga-simulator
An extended 6TiSCH simulator for slot bonding with a genetic algorithm (GA) scheduler

1) To let the simulator generate a topology based on experiment input parameters file. This is to be executed in the simulator/bin directory (Python 2.7):

        python runSim.py --genTopology=1 --topologyPath=../../topologies --json=../../input-example.json
   
2) To let the GA solve the slot bonding problem for the generated topology. This is to be executed in the main directory (> Python 3):

        python ga-heuristic.py -i input-example.json -l DEBUG

3) To let the simulator run the TSCH experiment, using the GA schedule allocations, for the given experiment, topology and schedule file. This is to be executed in the simulator/bin directory (Python 2.7):

        /usr/bin/python runSim.py --json=../../input-example.json --ilpfile=../../topologies/simulator-topology.json --ilpschedule=../../solutions/ga-schedule.json

The output of the simulation can be found in:
- bin/SimData/output_cpu0.dat
- topologies/simulator-topology.json
- solutions/ga.json

Additional directories:
- The p_files directory contains the probability data for the throughput calculations (see eq. 2 in the paper), for different reliabilities from 0.7 to 1.0, for an r_max of 4.
- The results-measurements-original directory contains the data necessary for the Modulation.py module that uses real-world measured data for the different OFDM modulations used by the simulator. This data can also be found in this repository: https://github.com/imec-idlab/adaptive-mcs-ofdm-measurements
