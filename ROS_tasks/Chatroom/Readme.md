## Chatroom
### Description of the Task and Approach Undertaken

#### 1. Creating the ROS2 Package
A new ROS2 package name chatroom is created using the command `ros2 pkg create --build-type ament_cmake chatroom`. The package follows the ament_cmake build system

#### 2. Implementing the Chat Client Node
A C++ node named chatroom_client was implemented within the packages.
* Publishes messages<br>
* Filters messages so that a client does not display its own messages.<br>
* Handles user input in a separate thread<br>
#### 3. Modifying Build and Dependency Files
* `CMakeLists.txt` is updated to make the chatroom_client executable and also link it with required dependencies (rclcpp and std_msgs).<br>
 making the file executable
`add_executable(chatroom_client src/chatroom_client.cpp)`
`ament_target_dependencies(chatroom_client rclcpp std_msgs)`
* `package.xml` is modified to include necessary dependencies.<br>
  `<depend>rclcpp</depend>`<br>
  `<depend>std_msgs</depend>`<br>
#### 4. Building the Package
The package is built using colcon build, ensuring that all dependencies were correctly linked and compiled.<br>
`colcon build --packages-select chatroom`
#### 7. Sourcing the setup file
`source install/setup.bash`
#### 6. Running Multiple Chat Clients
Users can launch multiple instances of the client with unique usernames, allowing real-time message exchange through the shared ROS2 topic.<br>
`ros2 run chatroom chatroom_client <User name>` 

### ROS Topics published 
#### 1. `/chatroom` (std_msgs/String)
Type: std_msgs/msg/String
Publisher: Each chatroom_client node publishes messages to this topic.<br>
Subscriber: Each chatroom_client node also subscribes to this topic.<br>
#### 2. Visualizing Communication with `rqt_graph`
The `rqt_graph` tool is a tool used u verify the number of nodes (clients) in the chatroom and also the type of connection among them.
#### Some Additioinal commands to find details about the user(client)
     `ros2 node list` --> lists all the active nodes.<br>
     `ros2 topic echo /chatroom` --> to see all the messages published in chatroom.<br>
     `ros2 node info <node_name>` --> to see the details of a specific node.<br>

### ROS Messages and services used

`std_msgs/msg/String`
Used to send chat messages between clients.<br>
Each message contains a username followed by the actual message<br> 

### RQT Graph
It helps us to understand, debug, and analyze how different nodes interact.<br>

![ROS2 Chatroom rqt_graph](https://github.com/MRM-AIA-TP2-2026/MRM_Anirudhha_U/blob/b2e69a56bbb79cb72943904e062cfcde6767fa17/ROS_tasks/Chatroom/RQT%20Graph.png)

![ROS2 Chatroom rqt_graph](https://github.com/MRM-AIA-TP2-2026/MRM_Anirudhha_U/blob/68ab6c67dd2127d48824b3644f20216df4d1bb73/ROS_tasks/Chatroom/RQT%20Graph1%20.png)

### Video link
https://youtu.be/I6hIzIbje1M

### Reference 
chatgpt 

    


