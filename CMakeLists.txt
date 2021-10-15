cmake_minimum_required(VERSION 3.0.2)
project(comms)

find_package(catkin REQUIRED 
	roscpp
	std_msgs
	sensor_msgs
	trajectory_msgs
	message_generation
)

add_message_files(
	FILES
	ObjectPose.msg
	ObjectsPoses.msg
	PoseStampedArray.msg
)

add_service_files(
	FILES
	AddObject.srv
	AddYCBObject.srv
	ExecTraj.srv
	ResetScene.srv
	SetColours.srv
	SimPushes.srv
	AddRobot.srv
	CheckScene.srv
	ResetArm.srv
	ResetSimulation.srv
	SetRobotState.srv
)

generate_messages(
	DEPENDENCIES
	std_msgs
	sensor_msgs
	trajectory_msgs
)

catkin_package(
  CATKIN_DEPENDS
  roscpp
  std_msgs
  message_runtime
)