# Emulsion Coalescence Simulation

The `CoalescenceSimulation` class is a tool that allows you to simulate the behavior of a particle emulsion within a system. It is designed to simulate the coalescence of particles around a specified coalescence center. Coalescence is the process by which small particles cluster and merge into larger particles. This simulation enables you to explore various parameters such as the number of particles, viscosity, attraction and repulsion forces, temperature, pH, and more.

## How to Use

Here's a step-by-step guide on how to use the `CoalescenceSimulation` class:

1. **Import the Required Libraries**

   Make sure you have the following Python libraries installed: `numpy`, `matplotlib`, `os`, `zipfile`, and `subprocess`.

   ```python
   import numpy as np
   import matplotlib.pyplot as plt
   import os
   import zipfile
   import subprocess
   ```

2. **Initialize the Simulation**

   Create an instance of the `CoalescenceSimulation` class by specifying the simulation parameters:

   ```python
   n_particles = 100
   timesteps = 100
   max_velocity = 0.01
   coalescence_center = (0.5, 0.5)
   output_folder = 'output_images'
   output_zip_file = 'coalescence.zip'
   output_video_file = 'coalescence.mp4'
   particle_radius = 0.01
   viscosity = 0.1
   surface_attraction = 0.005
   temperature = 298  # 25°C
   pH = 7.0
   ```

3. **Select the Interaction Potential Type**

   You can choose from three types of interaction potentials: "Lennard-Jones," "Exponential Repulsion," or "Linear Attraction." The user will select the type interactively:

   ```python
   # Ask the user to select the type of interaction potential
   print("Select the type of interaction potential:")
   print("1. Lennard-Jones")
   print("2. Exponential Repulsion")
   print("3. Linear Attraction")

   interaction_type = input("Enter the number of your choice (1/2/3): ")

   if interaction_type == "1":
       interaction_type = "lennard-jones"
   elif interaction_type == "2":
       interaction_type = "exponential-repulsion"
   elif interaction_type == "3":
       interaction_type = "linear-attraction"
   else:
       print("Invalid choice. Using Lennard-Jones potential by default.")
   ```

4. **Run the Simulation**

   Create the `CoalescenceSimulation` object and run the simulation:

   ```python
   coalescence_sim = CoalescenceSimulation(n_particles, timesteps, max_velocity, coalescence_center, output_folder, output_zip_file, output_video_file, particle_radius, viscosity, surface_attraction, temperature, pH, interaction_type)
   coalescence_sim.run_simulation()
   ```

5. **Explore the Results**

   After running the simulation, you will get a visual representation of the coalescence process, including images and a video saved in the specified output folder. You can analyze and further investigate the behavior of the emulsion under different conditions.

That's it! You can now use the `CoalescenceSimulation` class to conduct emulsion coalescence simulations and explore the effects of various parameters and interaction potentials.
