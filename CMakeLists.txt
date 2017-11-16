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
    gender_and_age_msgs
    uuid_msgs           
    move_base_msgs           # ros-planning/navigation
    control_msgs             # https://github.com/ros-controls/control_msgs.git
    actionlib
    people_msgs
    dynamic_reconfigure
    nodelet
    openni2_tracker_msgs
    tobi_world_msgs
    openpose_ros_msgs
    naoqi_bridge_msgs
    planning_scene_manager_msgs
    object_tracking_msgs
    augmented_manipulation_msgs
    moveit_msgs
    octomap_msgs
    biron_posture_execution_msgs
    object_recognition_msgs
    grasping_msgs
)


##############################################################################
# Catkin
##############################################################################

find_package(catkin REQUIRED genjava ${MESSAGES})



generate_rosjava_messages(
  PACKAGES ${MESSAGES}
)

catkin_package()

##############################################################################
# Installation
##############################################################################

install(DIRECTORY ${CATKIN_DEVEL_PREFIX}/${CATKIN_GLOBAL_MAVEN_DESTINATION}/org/ros/rosjava_messages/ 
        DESTINATION ${CATKIN_GLOBAL_MAVEN_DESTINATION}/org/ros/rosjava_messages)
