cmake_minimum_required(VERSION 2.8.3)
project(misc_utilties)

find_package(catkin REQUIRED)

find_package(catkin REQUIRED COMPONENTS 
  std_msgs 
  sensor_msgs 
  cv_bridge
  cmake_modules
)

catkin_python_setup()

generate_messages(
  DEPENDENCIES 
  std_msgs 
  sensor_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES error_calculation
#  CATKIN_DEPENDS message_runtime
  DEPENDS std_msgs sensor_msgs
)

include_directories(include
  ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY resource
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
