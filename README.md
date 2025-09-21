# 🛰️ Interactive Spacecraft Attitude Control Simulator

This repository contains a fun and interactive Jupyter Notebook that lets you take control of a tumbling satellite in space. Using a realistic physics simulation, your mission is to adjust the controller gains in real-time to stabilize the satellite and align it with a target orientation.

![WhatsApp Image 2025-09-20 at 13 37 52_66a2d6ce](https://github.com/user-attachments/assets/c670e3b3-2d9a-42f8-94ec-9e3ffb60c389)


## ✨ Features

-   **Real-Time Interactive Control**: Use sliders to adjust the Proportional (`Kp`) and Derivative (`Kd`) gains of the controller and see the effect immediately.
-   **Realistic 3D Visualization**: Watch the satellite, complete with a main body and solar panels, maneuver in a 3D space environment with a star-like background.
-   **Clear Target Visualization**: The target orientation is shown as a set of "ghost" axes, making it easy to see the goal of your maneuver.
-   **Optional Data Plots**: For a deeper analysis, you can toggle the display of 2D plots showing the satellite's attitude and angular velocity over time.
-   **Educational Explanations**: The notebook is filled with markdown cells explaining the core concepts of the physics and control theory involved.

## 🚀 How It Works

The simulation is built on the fundamental principles of rotational dynamics and control theory.

1.  **Physics Model**: The core of the simulation is **Euler's equations of motion**, which describe how a rigid body's rotation changes in response to applied torques. The satellite's orientation is represented using **quaternions** to avoid issues like gimbal lock.

2.  **PD Controller**: A Proportional-Derivative (PD) controller is used to generate the control torque needed to stabilize the satellite.
    *   **Proportional (P) term `Kp`**: This term applies a torque that is proportional to the **error** between the current orientation and the target. It's the main driver for correction. A larger `Kp` means a stronger push towards the target.
    *   **Derivative (D) term `Kd`**: This term applies a torque that is proportional to the **rate of change of the error** (i.e., the angular velocity). It acts as a damping force, preventing the satellite from overshooting the target and oscillating.

3.  **Interactive Simulation**: The Jupyter Notebook uses `ipywidgets` to create interactive sliders and checkboxes. When a user adjusts a control:
    *   The new controller gains (`Kp`, `Kd`) or target angles are sent to the simulation function.
    *   The system's differential equations are solved numerically using SciPy's `solve_ivp`.
    *   The results are visualized through the real-time 3D animation and optional 2D plots.

## 🔧 How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/stuti-bot/spacecraft_attitude_control_simulator.git
    cd spacecraft_attitude_control_simulator
    ```
2.  **Set up a Python environment and install dependencies:**
    ```bash
    python -m venv .venv
    # On Windows:
    .venv\Scripts\activate
    # On macOS/Linux:
    source .venv/bin/activate
    
    pip install -r requirements.txt
    ```
3.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook attitude_control_simulator.ipynb
    ```
4.  Run all the cells and interact with the sliders to control the satellite!

