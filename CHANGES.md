## Version 0.4.0

- Made synMech params independent of cell and referenced by labels (similar to NeuroML)

- Keep Neuron objects after sim so can explore, modify and/or rerun sim.

- Only gather data via py_alltoall if running on more than 1 node

## Version 0.3.9

- Fix recording of single cell of population when using MPI

- Fixed raster plotting based on NCD when using MPI

- Replaced save as .txt format with save as .csv

## Version 0.3.8

- Fixed bug when importing distributed mechanisms of cells

- importCell can use either *args or **kwargs

- Fixed bug in secLists implementation

- Removed mpl_toolkits.mplot3d import (unused and produced error in some Mac OS versions)

## Version 0.3.7

- Made conn functions more efficient using gid2lid and lid2gid

- Replaced 'syn' (synapse) with 'synMech' (synaptic mechanism) to avoid confusion with synaptic connections

## Version 0.3.6

- Fixed bug: STDP objects need to be stored so it works.

- Added support for SectionLists (modified format of importCell so also works)

- Fixed bugs: function-based connectivity 

## Version 0.3.5

- Fixed bugs: not checking connectivity rule conditions properly

- Fixed bug: number of connections depended on number of nodes

## Version 0.3.4

- Added option to add STDP plasticity and RL to connections

- Added option to run function at intervals during simulation, e.g. to interface with external program (such as virtual arm)

## Version 0.3.3

- Moved plot legend outside of plot area

- Changed order of raster population colors to make separation clearer

- Added option to select what cells to record/plot from separately; using new format with cells/pops in single list.

## Version 0.3.2

- Fixed bug: convergence connectivity produced error if used numeric value

## Version 0.3.1

- Added option to show and/or save to file the timing of initialization, cell creation, connection creation, setup recording, simulation run, data gathering, plotting, and saving. 

- Fixed bug: h.dt now set to value of simConfig['dt']

## Version 0.3

First version that was uploaded to pypi. Includes following features:

- Clear separation (modularization) of parameter specifications, network instantiation and NEURON simulation code.

- Easy-to-use, standardized, flexible, extensible and NEURON-independent format to specify parameters:
	- Populations
	- Cell property rules
	- Connectivity rules
	- Simulation configuration

- Support for cell location (eg. cortical depth) dependence of cell density and connectivity.

- Easy specification, importing and swapping of cell models (eg. point neuron vs multicompartment)

- Support for hybrid networks eg. combining point and multicompartment neurons.

- Multiple connectivity functions (eg. full, convergent, probabilistic) with optional parameters (eg. delay range)

- Support for user-defined connectivity functions.

- Populations, cell properties and connectivity rules can include reference to annotations (eg. for provenance).

- NEURON-independent instantiation of network (all cells, connections, ...) using Python objects and containers.

- NEURON-specific instantiation of network ready for simulation.

- Enables sharing of Python-based network objects, which can then be instantiated and simulated in NEURON.

- Easy MPI parallel simulation of network, including cell distribution across nodes an gathering of data from all nodes.

- Analysis and visualization of network (eg. connecitivity matrix) and simulation output (eg. voltage traces, raster plot)

- Data exporting/sharing to several formats (pickle, Matlab, JSON, HDF5) of the following:
	- Parameters/specifications
	- Instantiated networks
	- Simulation results