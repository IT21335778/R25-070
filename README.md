# R25-070

# IoT-Based Real-Time Mobile Robot Platform for Super Market Robot

##  Project Overview

This research explores the development and implementation of an autonomous mobile robot system designed for dynamic retail environments, such as supermarkets and warehouses. The primary objective of this project is to create a seamless integration of real-time localization, collision avoidance, and mobile application interaction, enabling autonomous robots to efficiently navigate complex and crowded spaces while ensuring safety and enhancing user interaction.

## 🧠 Problem Statement
The growing demand for automation in retail environments requires autonomous robots that can navigate complex, dynamic spaces like supermarkets and warehouses. However, existing solutions often rely on expensive technologies like LiDAR for localization and obstacle detection, which are costly and power-intensive. Additionally, separating path planning and obstacle detection leads to inefficiencies and risks of collisions in crowded areas. There is also a lack of effective mobile app integration for real-time user interaction and remote monitoring, which limits the scalability and functionality of these systems in retail settings.

This research seeks to address these challenges by developing an autonomous mobile robot system that integrates marker-based localization, AI-driven collision avoidance, and mobile application integration into a unified platform. By eliminating the reliance on costly technologies like LiDAR and offering a seamless user interface for remote monitoring and control, this solution aims to provide an adaptable, scalable, and efficient solution for autonomous navigation in retail spaces.


## 🎯 Objectives

**Develop a Cost-Effective Localization System** using ArUco markers, Inertial Measurement Units (IMUs), and wheel encoders, providing precise positioning without the need for expensive LiDAR technology.
**Implement AI-Driven Collision Avoidance** To integrate AI-based object detection models and multi-sensor fusion to identify and avoid both static and dynamic obstacles in real-time.
**Enhance Path Planning and Navigation** To develop an adaptive path planning algorithm that combines graph-based algorithms (A, PRM, RRT)* and reinforcement learning for real-time route optimization and dynamic re-routing based on environmental changes and obstacle detection.
**Ensure Safety and Compliance in Retail Environments** To implement safety features such as collision avoidance, emergency stop mechanisms, and real-time status updates to ensure the robot operates safely in dynamic, human-populated environments like supermarkets.

## 🧩 System Architecture
The system consists of four major subsystems:

### 🔍 Localization  Subsystem 

-uses**ArUco markers,IMU sensors and wheel encoders**
-implements
  -**Hybrid LocalizationZ**: Combining ArUco marker detection with IMU sensors and wheel encoders for continuous position tracking.
  -**Fallback Systems**: If ArUco markers are not visible, the system will rely on RGB-D cameras and optical flow algorithms to maintain accurate localization.
  -**ArUco Marker-based Localization**: Uses ArUco markers placed throughout the store to determine the robot's position with high accuracy.
  
-designed to
  -Ensure high localization accuracy even in featureless or dynamic areas by integrating sensor fusion techniques.
  -Allow the system to adapt to changes in the environment.

  
### 🔊 Collision Avoidance and Obstacle Detection

-uses
  -**RGB-D cameras, ultrasonic sensors, and infrared sensors** to detect and classify static and dynamic obstacles
  -**AI-based object detection models like YOLO and U-Net** to identify obstacles and differentiate between human and non-human objects.

-implements
  -**Predictive Modeling**: Uses LSTM networks and MediaPipe tracking to anticipate human movement and prevent collisions with pedestrians.
  -**Dynamic Window Approach (DWA)**: This real-time velocity control algorithm enables the robot to adjust its speed and path to avoid obstacles while maintaining efficient movement.
  -**Multi-Sensor Fusion**: Combines inputs from RGB-D cameras, ultrasonic sensors, and infrared sensors for comprehensive environmental perception.

-designed to
  -Ensure safe navigation in busy retail spaces, where obstacles can appear suddenly and change rapidly.
  -Adapt in real-time to moving obstacles such as people, carts, and other robots.
  -Minimize risk by enabling proactive collision avoidance, even in unpredictable and crowded environments.

### 📡 Path Planning and Navigation Subsystem 

-uses
  -Path generation for optimal movement from one point to another within the store.
  -Dynamic adjustments to avoid obstacles and reroute as necessary based on real-time sensor input.

-implements
  -**Graph-Based Algorithms**: A*, Dijkstra's, and PRM (Probabilistic Roadmap) are used for initial path planning based on the robot's starting point and destination.
  -**Dynamic Window Approach (DWA)**: Adjusts the robot's velocity and direction in real-time to avoid obstacles and optimize speed.
  -**Reinforcement Learning (Deep Q-Networks)**: Enhances path planning with AI-driven decision-making, allowing the robot to learn optimal avoidance strategies from interactions with its environment.

-designed to
  -Optimize robot efficiency by adjusting paths based on available space and predicted human movements in real-time.
  -Ensure real-time adaptability and responsiveness to dynamic retail settings, such as crowded aisles and frequent changes in store layout.
  
### 📈  Mobile Application and User Interface Subsystem

-uses
  -Notifications to alert users about obstacles, changes in the robot’s status, and task completion.
  -Real-time tracking of the robot’s location within the store.

-implements
  -Real-Time Communication: Utilizes MQTT messaging protocol for low-latency, real-time communication between the mobile app and robot.
  -Augmented Reality (AR): Integrates AR features to help customers locate products and navigate the store.
  -Interactive Dashboard: Provides a user-friendly interface for monitoring robot movement, task status, and environmental feedback.

## 🧪 Technologies Used

-**Arduino,Raspberry Pi / NVIDIA Jetson Nano,Python,C++,Robot operating system (ROS),Opencv,TensorFlow / PyTorch** (for firmware and data processing)
-**LoRaWAN,WebSockets,MQTT** (Communication Technologies)
-**Reinforcement Learning (DQN),LSTM (Long Short-Term Memory Networks),U-Net,YOLO (You Only Look Once)** (Machine Learning and AI Frameworks)
-**Energy-efficient Computing,Battery Management System** (Power and Energy Management Technologies)


## 📊 Data Requirements

-Real-Time Sensor Input: Proximity Sensors,Proximity Sensors,Human Detection(Data from MediaPipe model for human movement prediction and obstacle avoidance.),Localization Data (Position and orientation data from ArUco markers, IMU sensors, and wheel encoders to estimate the robot’s location.)
-Environmental Conditions: Lighting Conditions,Temperature and Weather
-Behavioral Patterns: Human Interaction Patterns,Robot Movement Data
-System Performance: Detection Accuracy,Navigation Efficiency,Collision Avoidance Effectiveness,Battery Health and Power Consumption

## 🧠 Domain Knowledge Applied

**Robotics and Automation**: Path Planning and Navigation,Robotics Systems Engineering
**Machine Learning and Artificial Intelligence**: Predictive Modeling,Reinforcement Learning,Computer Vision
**Localization and Mapping**: Sensor Fusion,Simultaneous Localization and Mapping (SLAM)
**Human-Robot Interaction (HRI)**: Context-Aware Computing,Mobile Application Development
**Sensor Technologies**: Real-Time Data Processing,Ultrasonic, Infrared, and RGB-D Sensors
**Power Management and Energy Efficiency**: Energy-Efficient Robotics
**IoT and Cloud-Based Communication**: Cloud Computing,IoT Communication Protocols
**Software Engineering and Integration**: Real-Time Software Development,Modular Software Design

## 🚀 Future Enhancements

-**Integration with Store Inventory Management Systems:** To enable the robot to interact directly with the store’s inventory system, providing more intelligent automation and assistance.
-**AI-Powered Human-Robot Interaction:** To improve customer engagement and create a more interactive shopping experience.
-**Enhanced Object Detection Capabilities:** Develop a custom object detection model tailored to the retail environment, such as distinguishing between various product types, customers, and obstacles with greater accuracy.
-**Real-Time Adaptive Path Planning:**  Implement reinforcement learning-based path planning that adapts in real-time to changes in the environment, such as new obstacles or human movement patterns.

## 👥 Contributors

Wijesinghe M L P -IT21335778
Wickramage M P W -IT21337376

## 📝 License
This project is licensed under the MIT License. See `LICENSE` for more information.

## 📬 Contact
For questions or collaboration inquiries, please contact the team through the project supervisor:

**Supervisor:** Ms. Thamali Kelegama E-mail: thamali.k@sliit.lk
**Co-Supervisor:** Mr. Dinith Primal E-mail: dinith.p@sliit.lk
