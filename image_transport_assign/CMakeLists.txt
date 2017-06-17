cmake_minimum_required(VERSION 2.8.3)
project(image_transport_assign)


find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs genmsg)


add_message_files(FILES Num.msg)



generate_messages(DEPENDENCIES std_msgs)


catkin_package()


include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(impub src/impub.cpp)
target_link_libraries(impub ${catkin_LIBRARIES})
add_dependencies(impub numbers_generate_messages_cpp)

add_executable(imsub src/imsub.cpp)
target_link_libraries(imsub ${catkin_LIBRARIES})
add_dependencies(imsub numbers_generate_messages_cpp)


