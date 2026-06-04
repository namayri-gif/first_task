# Part 1: ROS2 Publisher and Subscriber Package
## Project Description

This project was developed using ROS2 Jazzy and Python. The goal was to understand the fundamentals of ROS2 communication by creating a custom publisher node and subscriber node that exchange messages through ROS topics.

## What Was Built and Why

A ROS2 package named `my_first_package` was created containing:
* `simple_publisher.py`
* `simple_subscriber.py`
The publisher node continuously publishes messages to a ROS topic, while the subscriber node listens to the same topic and displays the received messages.
This task was completed to gain hands on experience with:
* ROS2 nodes
* Topics
* Publishers and subscribers
* Package creation and building using `colcon`

## What I Learned

Through this task, I learned:
* How ROS2 nodes communicate using topics
* How to create Python based ROS2 packages
* How to build a workspace using `colcon build`
* How to source a ROS2 workspace
* How to run publisher and subscriber nodes
* Basic ROS2 command line tools for debugging and monitoring topics


## Setups and Creation:
<img width="973" height="573" alt="image" src="https://github.com/user-attachments/assets/fa1f2abc-c5a5-47c9-b0db-c53d0dbe9bf6" />
<img width="942" height="276" alt="image" src="https://github.com/user-attachments/assets/81f2cf05-5495-4bbe-a44a-099dec97ded4" />

## Running Publisher and Subscriber
<img width="894" height="694" alt="image" src="https://github.com/user-attachments/assets/8c9932ba-ec4e-4b89-97d7-b474c6124520" />
<img width="1169" height="664" alt="image" src="https://github.com/user-attachments/assets/0590dbd4-c5fa-47d2-b32b-1fbea7252e0a" />


# Part 2: TurtleBot3 Control Topics

## Project Description
This task focused on understanding how TurtleBot3 receives motion commands in ROS2. The main objective was to identify the velocity control topic and test manual movement commands using ROS2 command line tools.

## What Was Built and Why
In this task, the TurtleBot3 motion control topic was tested using the `/cmd_vel` topic. This topic is used to send velocity commands to the robot.
The velocity command uses the `geometry_msgs/msg/Twist` message type, which contains:
* Linear velocity
* Angular velocity

  
This was done to understand how the robot moves forward, backward, and rotates inside the Gazebo simulator.

[In this part, no additions and changes where made to the code so no pictures to be attached]
## What I Learned

Through this task, I learned:

* TurtleBot3 is controlled through the `/cmd_vel` topic
* `Twist` messages are used to control robot velocity
* `linear.x` controls forward and backward movement
* `angular.z` controls left and right rotation
* ROS2 topics can be inspected using `ros2 topic list` and `ros2 topic info`
* Manual commands can be published using `ros2 topic pub`

## Useful Commands

### List ROS2 Topics
```bash
ros2 topic list
```
### Check the Control Topic
```bash
ros2 topic info /cmd_vel
```
### Move TurtleBot3 Forward
```bash
ros2 topic pub -r 10 /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.2}, angular: {z: 0.0}}"
```
### Rotate TurtleBot3
```bash
ros2 topic pub -r 10 /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0}, angular: {z: 0.5}}"
```
### Stop TurtleBot3
```bash
ros2 topic pub --once /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0}, angular: {z: 0.0}}"
```

