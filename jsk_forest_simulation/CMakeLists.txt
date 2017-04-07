cmake_minimum_required(VERSION 2.8.3)
project(jsk_forest_simulation)

set(PACKAGE_DEPENDENCIES
  roscpp
  std_msgs
  geometry_msgs
)

find_package(cmake_modules REQUIRED)
find_package(catkin REQUIRED ${PACKAGE_DEPENDENCIES})

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS ${PACKAGE_DEPENDENCIES}
)

set(LINK_LIBS
  ${catkin_LIBRARIES}
)

add_executable(uav_teleop_keyboard src/uav_teleop_keyboard.cpp)
target_link_libraries(uav_teleop_keyboard ${LINK_LIBS})
