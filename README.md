# SmolVLA

## About the project

This project uses the **MuJoCo physics engine** to simulate and control two robots:

1. A **6-DOF robot manipulator** that performs forward kinematics, inverse kinematics, PD control, and a complete **pick-and-place** task.
2. A **quadruped robot** that stands up, balances against a push, and moves forward across the floor using a **trot gait**.

## Tech stack

- **Python** for simulation scripts, robot control, and visualization.
- **MuJoCo** for physics simulation and interactive model viewing.
- **MJCF/XML** for robot models and scene definitions.
- **MuJoCo Menagerie** for loading supported robot models and variants.
- **venv and pip** for environment and dependency management.

## Instructions for setup

Create and activate a virtual environment, then install the dependencies:

```bash
python3 -m venv mojoco_venv
source mojoco_venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

## Load models and visualize

The robot visualization scripts are `arm/arm_viewer.py` and `quadruped/quadruped_viewer.py`.

```bash
# Open the interactive arm viewer (default custom model: arm6dof.xml)
python arm/arm_viewer.py

# Open the quadruped viewer
python quadruped/quadruped_viewer.py

# Record a headless demo video
python arm/arm_viewer.py --video

# Load a MuJoCo Menagerie model
python arm/arm_viewer.py --menagerie <model_name>

# Load a specific scene (default: scene.xml)
python arm/arm_viewer.py --menagerie <model_name> --scene <scene_file>

# Record a video of the model gently waving its actuators
python arm/arm_viewer.py --menagerie <model_name> --video

# Load a model variant
python arm/arm_viewer.py --menagerie <model_name> --variant <variant_name>
```
