# Laminar Flow over 2D Cylinder at Reynolds Number = 100 
#### Simulation is performed using OpenFOAM v1912 and postProcessing is performed using Paraview 5.8.1
This is a part of our project titled **Flow over Rough and Engineered Surfaces** carried out under school of Mechanical Sciences, Indian Institute of Technology Goa:
- Authors : Jainam Jain, Tushya Chheda
- Guidance : Dr. Sudhakar Yogaraj
- Email : {jainam.jain.18003, tushya.chheda.18003,sudhakar}@iitgoa.ac.in

Simulation was carried on a machine running with Ubuntu 18.04. Serial as well as parallel modes were used.

## Overview:
#### Aim is to calculate the Drag Coefficient(Cd) and Strouhal's Number and verify them with the literature.
#### Specifications:
- Reynolds Number = 100
- Diameter of the Cylinder = 1 m
- Inlet Velocity = 1 m/s
- Kinematic Viscosity = 0.01 m2/s

## Domain Description:

The domain is a cuboid of length 33m, height 16m and depth 1m. The Bounding Box is (-8 -8 -0.5) (25 8 0.5). The cylinder is located at origin(0 0 0). The cylinder is fixed with diameter 1m which is taken as characteristic length. From the origin, the domain extends 25m to the east, 8m to north, 8m to south and 8m to west. The domain for fixed flow over circular cylinder can be seen in figure. 

The mesh is very fine near the periphery of the cylinder as well as in the wake region behind the cylinder to capture the vortex shedding of the flow. Grading is done to get coarser mesh at the boundries.  The total number of nodes (nPoints) are 120336. The total number of elements (nCells) are 59640. The images of mesh near the periphery of cylinder and overall are shown below: 

## Boundary Conditions: 
#### Velocity Conditions:
- Inlet  : 1 m/s (Ux = 1, Uy = 0, Uz = 0)
- Outlet : zero Gradient
- Top    : symmertryPlane
- Bottom : symmetry Plane
- Cylinder : noSlip

#### Pressure Conditions : 
- Inlet  : zero Gradient
- Outlet : 0 Pascal
- Top    : symmetryPlane
- Bottom : symmetryPlane
- Cylinder : zeroGradient

## Running the Case:
1. To Mesh: 
> $ blockMesh

2. To check Mesh quality:
> $ checkMesh

3.To run simulation in serial: 
> $ icoFoam

4.To run simulation in parallel:

    a. First Decompose the mesh in to number of sub-regions by running
> $ decomposePar

    b. To run the parallel simulations:
> $ mpirun -np 4 icoFoam -parallel

    c. Reconstruct the solution using:
> $ reconstructPar

5. Convert the files into VTK format(to visualize in Paraview)
> $ foamToVTK

6. The postProcessing is done using Paraview 5.8.1(select .vtu format file)

## Output:
The Drag Coefficient for Reynold's Number = 100 was verified with the literature. To calculate the Strouhals Number, Lift Coefficient(Cl) v/s Time is extracted from the solution and the main frequency was calculated using FFT(Fast Fourier Transformation) 



. 


