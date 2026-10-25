# What Affects Glider Winch Launch Height?

Final project for Introduction to Numerical Algorithms.

## Project idea

We want to investigate how different launch conditions affect the release altitude of a glider. We will build a simple 2D simulation in Python and compare the results while changing selected parameters.

The glider will start from rest with an adjustable ground acceleration. We will calculate its speed and distance until lift-off and check the required pulling force against the winch limits. After lift-off, the acceleration will be calculated from gravity, lift, drag and cable tension.

## Launch model

The launch will have four main stages:

1. Ground acceleration from rest until lift-off.
2. A shallow climb below an adjustable transition height, initially set to 30 m.
3. A smooth transition to a steeper climb.
4. A gradual reduction of the climb angle near the top, followed by cable release.

We will assume constant horizontal wind and a straight, massless cable. Lift-off will depend on airspeed and lift. Available glider polar data will be used to build an approximate aerodynamic model.

The 30 m threshold is a model assumption.

## Research questions

How does release altitude change with:

- Ground acceleration and wind speed?
- Total glider mass and starting distance from the winch?
- Initial and upper climb angles?
- The length of the transition between climb stages?
- When and how gradually the climb angle is reduced before release?
- Available winch force and power?
- Glider type and its polar characteristics?

We will first change one parameter at a time, keeping the others fixed. Then we will study selected combinations and search for climb profiles that give a higher release altitude within the model limits.

## Numerical methods

- **Euler and RK4:** calculate the motion and compare time steps.
- **Bisection:** locate lift-off and release events.
- **Trapezoidal and Simpson rules:** integrate cable power to calculate work.
- **Interpolation and curve fitting:** build an approximate aerodynamic model from polar data.
- **Simulated annealing:** search for better climb profiles and compare with a parameter grid.

We will check convergence, test cases with known solutions and reject runs that exceed the chosen speed, load, cable force or power limits.

## Planned results

We will plot trajectories, altitude and airspeed over time, and release altitude against each parameter. Heatmaps will show the effects of changing two parameters together.

Tools: Python, NumPy, SciPy, Matplotlib and Jupyter Notebook.

**Current status:** planning stage. Running instructions will be added when the code is ready.

Reference: [Numeric simulation of a glider winch launch](https://publications.rwth-aachen.de/record/230129), Christoph Georg Santel.
