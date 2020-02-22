cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
project(MY_GRAND_PROJECT)

find_package(PCL 1.3 REQUIRED)
find_package(realsense2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

add_executable(pcltest test.cpp)
target_link_libraries(pcltest ${PCL_LIBRARIES})
target_link_libraries(pcltest ${realsense2_LIBRARY})

add_executable (range_image_visualization range_image_visualization.cpp)
target_link_libraries (range_image_visualization ${PCL_LIBRARIES})

add_executable (cloud_viewer cloud_viewer.cpp)
target_link_libraries (cloud_viewer ${PCL_LIBRARIES})

add_executable (iterative_icp iterative_icp.cpp)
target_link_libraries (iterative_icp ${PCL_LIBRARIES})

add_executable (downsample_vox voxel_grid.cpp)
target_link_libraries (downsample_vox ${PCL_LIBRARIES})
