cmake_minimum_required(VERSION 3.8)
project(chatroom)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)

add_executable(chatroom_client src/chatroom_client.cpp)
ament_target_dependencies(chatroom_client rclcpp std_msgs)

install(TARGETS
  chatroom_client
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()

