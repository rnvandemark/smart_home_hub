cmake_minimum_required(VERSION 3.0.2)
project(smart_home_hub)

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
	nodes/SmartHomeHubRunner
	scripts/SmartHomeHubNodeInterface.py
	scripts/SmartHomeHubController.py
	scripts/GUI.py
	DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
install(
	DIRECTORY assets/
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/assets
)
