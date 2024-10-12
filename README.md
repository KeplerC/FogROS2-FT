# FogROS2-FT: Fault Tolerance 

This is a meta package that sets up FogROS2-FT. The project website can be found [here](https://sites.google.com/view/fogros2-ft).

### Download 
To download the repository and all submodules, run:
```bash
mkdir -p ~/ft_ws/src
cd ~/ft_ws/src
git clone https://github.com/KeplerC/fogros2-ft.git src
git submodule update --init --recursive
```


### Install
We assume a Ubuntu 22.04 system with ROS2 Humble and colcon installed. 
```bash
sudo apt install build-essential curl pkg-config libssl-dev protobuf-compiler clang
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source "$HOME/.cargo/env"
pip install skypilot[aws]
```
You can configure AWS by running `aws configure` and run 
```bash
sky check
```
to make sure your AWS is correctly configured. 

Then build the workspace:
```bash
cd ~/ft_ws
colcon build
```

### Run the example
All the examples can be found in [directory](./FogROS2-sky/fogros2_examples/launch/), which you can run by:
```bash
source ~/ft_ws/install/setup.bash
ros2 launch fogros2_examples <example_name>.sky.launch.py
```
You are not required to install rust related dependencies to run the docker examples, which you can directly run by:
```bash
cd ~/ft_ws
ros2 launch fogros2_examples <example_name>.docker.sky.launch.py
```

### References
- All Cloud Robotics Application Code: https://github.com/BerkeleyAutomation/fogros-realtime-examples 
- All raw logs to generate paper figures: https://github.com/BerkeleyAutomation/fogros-rt-results 
