# ROS2 Intro Project – Python & C++ Nodes

This repository contains hands-on ROS2 packages developed during the "ROS2 for Beginners" course. It demonstrates core ROS2 concepts using both Python (`rclpy`) and C++ (`rclcpp`), including publishers, subscribers, services, parameters, and launch files.

## 📦 Packages

- `my_py_pkg`: Python nodes for publishing and counting integers, with dynamic parameters and service-based reset.
- `my_cpp_pkg`: C++ nodes (not shown here) implementing similar logic for performance comparison.
- `my_robot_bring_up`: Launch files to start multiple nodes and simulate robot news stations.
- `my_robot_interfaces`: Custom message/service definitions (if applicable).

## 🧠 Key Concepts Demonstrated

- **Publisher/Subscriber**:  
  - `NumberPublisherNode`: Publishes integers at a configurable rate.  
  - `NumberCounterNode`: Subscribes to integers, maintains a running total, and publishes the count.

- **Services**:  
  - `AddTwoIntsServerNode`: Accepts two integers and returns their sum.  
  - `NumberCounterNode`: Offers a `reset_counter` service using `SetBool`.

- **Parameters**:  
  - Dynamic configuration of `number` and `timer_period` via ROS2 parameters.

- **Launch Files**:  
  - Launch multiple nodes with parameterized robot names (e.g. Giskard, BB8, C3PO) using YAML configuration.

## 🚀 How to Build & Run

```bash
# Build the workspace
colcon build

# Source the setup
source install/setup.bash

# Run nodes
ros2 run my_py_pkg number_publisher
ros2 run my_py_pkg number_counter
ros2 run my_py_pkg add_two_ints_server

# Launch multiple robot stations
ros2 launch my_robot_bring_up robot_news_launch.py

🧪 Topics & Services
/number → Published by NumberPublisherNode

/number_count → Published by NumberCounterNode

/reset_counter → Service to reset the counter

/add_two_ints → Service to add two integers

👩‍💻 Author
Kyriaki Kostika
