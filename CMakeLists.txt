cmake_minimum_required(VERSION 3.0.2)
project(hub)

find_package(
	catkin REQUIRED COMPONENTS
	rospy
	smart_home_msgs
)
catkin_package(
	CATKIN_DEPENDS
	rospy
	smart_home_msgs
)
catkin_install_python(
	PROGRAMS
	hub/SmartHomeHubRunner
	hub/SmartHomeHubNodeInterface.py
	hub/SmartHomeHubController.py
	hub/GUI.py
	DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
install(
	DIRECTORY resource/
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/resource
)
