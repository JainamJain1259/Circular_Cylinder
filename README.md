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

##Domain Description:
The domain is a cuboid of length 33m, height 16m and depth 1m. The Bounding Box is (-8 -8 -0.5) (25 8 0.5). The cylinder is located at origin(0 0 0). The cylinder is fixed with diameter 1m which is taken as characteristic length. From the origin, the domain extends 25m to the east, 8m to north, 8m to south and 8m to west. The domain for fixed flow over circular cylinder can be seen in figure.



