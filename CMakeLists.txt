cmake_minimum_required(VERSION 3.5)
project(template_ros2_pkg)

################################################
## C++ Version instructions for Compiler
# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()


##########################
## Package Dependencies ##
##########################

find_package(ament_cmake REQUIRED)

## Add additional dependencies using this format
# find_package(<dependency> REQUIRED)

## Uncomment if installing Python scripts below
# find_package(ament_cmake_python REQUIRED)

## Uncomment if using autolinters
# find_package(ament_lint_auto REQUIRED)
# ament_lint_auto_find_test_dependencies()


###########
## Build ##
###########

# See https://docs.ros.org/en/rolling/How-To-Guides/Ament-CMake-Documentation.html
# See https://cmake.org/cmake/help/latest/guide/tutorial/index.html


#############
## Install ##
#############

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
## Ref: https://docs.ros.org/en/foxy/How-To-Guides/Ament-CMake-Python-Documentation.html#using-ament-cmake-python
# ament_python_install_package(${PROJECT_NAME})

## Mark executables for installation
# install(TARGETS ${PROJECT_NAME}_node
#   RUNTIME DESTINATION ${lib/${PROJECT_NAME}}
# )

## Mark libraries for installation
# install(TARGETS ${PROJECT_NAME}
#   ARCHIVE DESTINATION ${lib}
#   LIBRARY DESTINATION ${lib}
#   RUNTIME DESTINATION ${bin}
# )

## Mark cpp header files for installation
# install(DIRECTORY include/${PROJECT_NAME}/
#   DESTINATION ${include/${PROJECT_NAME}}
#   FILES_MATCHING PATTERN "*.h"
#   PATTERN ".svn" EXCLUDE
# )

## Mark other files for installation (e.g. launch and bag files, etc.)
# install(FILES
#   # myfile1
#   # myfile2
#   DESTINATION ${share/${PROJECT_NAME}}
# )


#############
## Testing ##
#############

## Add gtest based cpp test target and link libraries
# ament_add_gtest(${PROJECT_NAME}-test test/test_myPackage.cpp)
# if(TARGET ${PROJECT_NAME}-test)
#   target_link_libraries(${PROJECT_NAME}-test ${PROJECT_NAME})
# endif()

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()


###################################
## colcon specific configuration ##
###################################
# The only valid argument for ament_package is CONFIG_EXTRAS.
# All other arguments are covered by separate functions which
# all need to be invoked before ament_package:
# Call ament_export_dependencies(...) 	when building a reusable library.
# Call ament_export_include_directories(...) 	Allows compiler to search in this folder
#						in future packages.
# Call ament_export_libraries(...) 		paired with above *_include_directories.

ament_package()

#EOF
