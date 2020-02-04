cmake_minimum_required(VERSION 2.8.3)
project(zedyolo_msgs)


find_package(catkin REQUIRED
            geometry_msgs
            message_generation)
add_message_files(
    DIRECTORY msg
    FILES
    zed_raw.msg
)
generate_messages(
   DEPENDENCIES
   std_msgs
   geometry_msgs  
   )

catkin_package(
    CATKIN_DEPENDS geometry_msgs message_runtime
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h")