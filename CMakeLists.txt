cmake_minimum_required(VERSION 2.8.3)
project(face_classification)

find_package(catkin REQUIRED COMPONENTS
	rospy
  rospkg
  std_msgs
	sensor_msgs
	message_generation
  cv_bridge
)

## Generate messages in the 'msg' folder
add_message_files(
	DIRECTORY ros/msg
	FILES
	FaceClassification.msg
	FaceClassificationArray.msg
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
  rospy
  rospkg
  std_msgs
  sensor_msgs
  message_generation
  message_runtime
  cv_bridge
)

catkin_python_setup()