# CLI

## Information

#### Help -h&#x20;

#### Show Commands -c

#### Args -a

#### Show -s

## Modifiers

#### Step Size -ss&#x20;

$$
\delta x = \sqrt{2D_0\delta t}
$$

#### Permeation Probability -pp

$$
\frac {P}{P-1} = \frac {2\kappa \delta s}{D_0} \newline \
\newline \ 
 \small   
\delta s : Step\ Size\ 
 \newline \  \kappa : Membrane \ Permeability
$$

#### Intrinsic Diffusivity -d0

Intrinsic Diffusivity for each region

#### Init In -ii

Enumeration for starting conditions&#x20;

1. Initialize all particles inside.
2. Initialize particles freely inside bounding box.
3. Initialize particles at center of cell.&#x20;

#### Time Step -ts

$$
f(x) = x * e^{2 pi i \xi x}
$$

#### Voxel Size -vs

Set the voxel size for the simulation.

This is currently unavailable.

#### NStep -ns

Number of steps for the simulation&#x20;

$$
f(x) = x * e^{2 pi i \xi x}
$$

#### NPar -np&#x20;

$$
f(x) = x * e^{2 pi i \xi x}
$$



#### In Path:  -p&#x20;

The path of lookup table and simulation input data. If a new path is specified the simulation object will be deleted and reloaded with the updated data and configuration.

#### Out Path: -o

Specify a results directory.

#### Save All -sa

Specify whether to save all location data.&#x20;

#### Quit/Run  -q -Q -done

Start the simulation.
