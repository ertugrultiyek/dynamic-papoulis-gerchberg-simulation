# System Identification Project with ROS2 and Gazebo

## Purpose

This project aims to develop a simulated environment for system identification using ROS2 and Gazebo. By integrating a Velodyne VLP16 puck lidar and Xsens MTi 1-series IMU in a Gazebo-simulated indoor environment, the project facilitates the generation of controlled synthetic data to validate and refine system identification models. This approach allows for precise control over environmental variables and sensor inputs, providing robust datasets against which theoretical identification models can be tested and optimized.

## Features

- **Simulated Sensors:** Utilizes Velodyne VLP16 and Xsens MTi 1-series IMU for realistic data generation.
- **Controlled Testing Environment:** Offers a configurable indoor environment within Gazebo for diverse scenario testing.
- **ROS2 Integration:** Leverages ROS2 for efficient data handling and node management.
- **Docker-based Setup:** Ensures easy setup and reproducibility across various platforms, including ARM-based macOS systems.
- **Modular Architecture:** Supports easy customization and scaling through a well-organized project structure.

## Getting Started

### Prerequisites

- Docker
- ROS2 Foxy Fitzroy
- Gazebo 11
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/system-identification-ros2.git
   cd system-identification-ros2
   ```

2. **Build the Docker containers:**
   ```bash
   cd docker
   docker-compose build
   ```

3. **Run the simulation:**
   ```bash
   docker-compose up
   ```

### Usage

To start the simulation with default settings:

```bash
./scripts/run_containers.sh
```

For advanced configurations, modify the files in the `/config` directory to tune the simulation parameters for the lidar and IMU.

## User Manual

### Launching the Simulation

Use the provided launch files to start the simulation environment with the necessary sensors and data processors:

```bash
ros2 launch system_identification simulation_launch_file.launch.py
```

### Data Collection

Data generated from the simulation is stored in the `/data` directory. Use ROS2 tools to monitor, record, and analyze the data:

```bash
ros2 bag record -o my_simulation_output /sensor_topics
```

### System Identification Process

1. **Modify Identification Parameters:** Update the parameters in the `config/system_identification.yaml` to fit your specific model requirements.

2. **Run the Identification Scripts:**
   Navigate to the `/scripts` directory and execute:
   ```bash
   python3 perform_identification.py
   ```

## Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Your Name - [@your_twitter](https://twitter.com/your_twitter) - email@example.com

Project Link: [https://github.com/yourusername/system-identification-ros2](https://github.com/yourusername/system-identification-ros2)

## Acknowledgements

- [ROS2 Documentation](https://docs.ros.org/en/foxy/)
- [Gazebo Tutorials](http://gazebosim.org/tutorials)
- [Velodyne Simulation](https://bitbucket.org/DataspeedInc/velodyne_simulator/src/master/)
- [Xsens MTi ROS Driver](https://github.com/xsens/xsens_mti_ros_node)
```