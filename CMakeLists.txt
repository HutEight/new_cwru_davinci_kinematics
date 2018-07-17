cmake_minimum_required(VERSION 2.8.3)
project(cwru_davinci_kinematics)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages

find_package(Eigen3)

add_definitions(${EIGEN_DEFINITIONS})


find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  roslint
  tf2
  tf
  tf2_eigen
)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=gnu++0x")

include_directories(
        include
        ${catkin_INCLUDE_DIRS}
        ${catkin_INCLUDES}
        ${Eigen3_INCLUDE_DIRS}
)

catkin_package(
        DEPENDS ${Eigen3_DEP}
        LIBRARIES davinci_kinematics
        CATKIN_DEPENDS roscpp
        INCLUDE_DIRS include ${EIGEN3_INCLUDE_DIRS}
)
