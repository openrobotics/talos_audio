## Author: Devon Ash
## Maintainer: noobaca2@gmail.com

cmake_minimum_required(VERSION 2.8.3)
project(talos_audio)
find_package(catkin REQUIRED COMPONENTS message_generation rospy roscpp std_msgs)

catkin_python_setup()

add_service_files(
  FILES
  ListenForAll.srv
  ListenForAny.srv
  ListenFor.srv
)

generate_messages(DEPENDENCIES std_msgs)

catkin_package(
CATKIN_DEPENDS message_generation std_msgs
)

install(PROGRAMS src/talos_audio/talosaudio.py DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(DIRECTORY srv speech_dictionaries src launch DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

install(FILES setup.py README.md DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
