cmake_minimum_required(VERSION 2.8.3)
project(face_classification)

find_package(catkin REQUIRED COMPONENTS
	rospy
  	std_msgs
	sensor_msgs
	message_generation
)

catkin_python_setup()

## Generate messages in the 'msg' folder
add_message_files(
	DIRECTORY ros/msg
	FILES
	face_classification_single.msg
	face_classification_array.msg
)

add_service_files(
  DIRECTORY ros/srv
  FILES 
  face_classification_buffered.srv
  face_classification_continuous.srv
)

generate_messages(
  DEPENDENCIES 
  std_msgs
  sensor_msgs
)

catkin_package(
 CATKIN_DEPENDS
 message_runtime
)
