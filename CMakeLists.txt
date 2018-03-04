##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(rosjava_messages)

set(MESSAGES 
    roscpp                   # !!!!!!! REMOVE THIS ONCE https://github.com/ros-planning/navigation/pull/312 is fixed! !!!!!!!!

    std_msgs
    rosgraph_msgs            # ros/ros_comm_msgs
    std_srvs
    rosjava_test_msgs        # rosjava/rosjava_test_msgs
    actionlib_msgs           # ros/common_msgs
    diagnostic_msgs
    geometry_msgs
    nav_msgs
    sensor_msgs
    shape_msgs
    stereo_msgs
    trajectory_msgs
    visualization_msgs
    tf2_msgs                 # geometry_experimental/tf2_msgs
    tf
    uuid_msgs           
    move_base_msgs           # ros-planning/navigation
    control_msgs             # https://github.com/ros-controls/control_msgs.git
    actionlib
    people_msgs
    dynamic_reconfigure
    nodelet
    moveit_msgs
    octomap_msgs
    object_recognition_msgs
    grasping_msgs
    map_msgs
    pcl_ros
)


##############################################################################
# Catkin
##############################################################################

find_package(catkin REQUIRED genjava ${MESSAGES})



generate_rosjava_messages(
  PACKAGES ${MESSAGES}
)

catkin_package()
