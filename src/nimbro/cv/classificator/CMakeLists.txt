cmake_minimum_required(VERSION 2.8.3)
project(classificator)

find_package(catkin REQUIRED COMPONENTS roscpp nodelet calibration sensor_msgs)

include_directories(${catkin_INCLUDE_DIRS})

catkin_package()

add_library(classificator
	classificator.cpp
)

target_link_libraries(classificator
	${catkin_LIBRARIES}
)

install(TARGETS classificator
	LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)

install(FILES nodelet_plugins.xml
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
