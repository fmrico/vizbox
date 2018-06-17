cmake_minimum_required(VERSION 2.8.3)
project(vizbox)

find_package(catkin REQUIRED COMPONENTS
	message_generation
)

catkin_python_setup()

add_message_files(
  DIRECTORY msg
  FILES
    Story.msg
)
generate_messages(
  DEPENDENCIES
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
)

install(DIRECTORY scripts/
  USE_SOURCE_PERMISSIONS
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/
)
