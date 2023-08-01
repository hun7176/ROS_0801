cmake_minimum_required(VERSION 3.0.2)
project(pub_sub_dialog)

find_package(catkin REQUIRED COMPONENTS
    rospy
    roslaunch
    std_msgs
    message_generation
)
catkin_python_setup()

generate_messages(
    DEPENDENCIES
    std_msgs
)

catkin_package(
    CATKIN_DEPENDS
    rospy
    roslaunch
    std_msgs
    message_runtime
)

include_directories(
    include
    ${cation_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
    nodes/listener
    nodes/talker
    nodes/nodeCtrl
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
