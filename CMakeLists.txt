##############################################################################
# CMake
##############################################################################

cmake_minimum_required(VERSION 2.8.3)
project(rosjava_messages)

##############################################################################
# Catkin
##############################################################################

find_package(catkin REQUIRED genjava)

generate_rosjava_messages(
  PACKAGES
    std_msgs
    rosgraph_msgs            # ros/ros_comm_msgs
    std_srvs
    rosjava_test_msgs        # rosjava/rosjava_test_msgs
    actionlib_msgs           # ros/common_msgs
    common_msgs
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
    ar_track_alvar_msgs      # sniekum/ar_track_alvar_msgs
    uuid_msgs                # ros-geographic-info/unique_identifier
    yocs_msgs                # yujinrobot/yocs_msgs
    gateway_msgs
    world_canvas_msgs
    scheduler_msgs
    move_base_msgs           # ros-planning/navigation
    map_store                # ros-planning/map_store
    control_msgs             # https://github.com/ros-controls/control_msgs.git
    actionlib
    roscpp                   # !!!!!!! REMOVE THIS ONCE https://github.com/ros-planning/navigation/pull/312 is fixed! !!!!!!!!
    people_msgs
    dynamic_reconfigure_msgs
    dynamic_reconfigure
    nodelet
    nodelet_msgs
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

catkin_package()

##############################################################################
# Installation
##############################################################################

install(DIRECTORY ${CATKIN_DEVEL_PREFIX}/${CATKIN_GLOBAL_MAVEN_DESTINATION}/org/ros/rosjava_messages/ 
        DESTINATION ${CATKIN_GLOBAL_MAVEN_DESTINATION}/org/ros/rosjava_messages)
