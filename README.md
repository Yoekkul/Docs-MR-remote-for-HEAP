# What this project does
When working with autonomous construction machines it is essential to intuitively and quickly give commands adapt their work. This can be done most directly through the use of a Mixed Reality headset, which overlays sensor readings of the machine and presents an editing interface to the user.


# Implemented functions
From the [M545 excavator](https://rsl.ethz.ch/robots-media/heap.html) we can obtain the Machines position, as well as a Grid Map approximating the terrain seen by its LIDAR sensor. This is then visualized on the Hololens, where the virtual scene is aligned with the physcal world throught the use of QR codes in combination with Microsofts World Locking Tools. 

The Grid Map's density as well as the frequency of the updates are determined from the Hololens. The ROS client is then in charge of scaling down to the desired resolution. This is to avoid overtaxing the limited computation capabilities of the Hololens.




From the Hololens an user can toggle the model of the Excavators cabin on and off (this is for instance useful for an user sitting inside the machine who is then able to see what the Robots sensors see even though that view would be obstructed).

An user can also set "terrain editing nodes" through which the terrain can be edited on the fly. By setting one of the nodes above the terrains Grid Map a conical hill is created up to the height of the node. These nodes can be created, moved and deleted directly on the Hololens.

_Currently no Grid Map message is generated and sent back to the machine_

An additional feature is the ability to create and move of two markers. These are uploaded to the ROS server and can be used as target position for Inverse Kinematics based movement of the arm of the machine.


# Components
The code is subdivided into two main components: 
* Client: Running on the Hololens, written in C# on the Unity Game Engine 
* Server: ROS node sending sensor data to the Hololens as well as relaying instructions from the Hololens back to the excavator

## Unity Client

## ROS Server

# Future work

