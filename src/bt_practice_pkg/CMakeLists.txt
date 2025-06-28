cmake_minimum_required(VERSION 3.8)
project(bt_practice_pkg)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(behaviortree_cpp REQUIRED)
find_package(behaviortree_ros2 REQUIRED)

add_executable(bt_u2_ex2 src/bt_u2_ex2.cpp)
add_executable(bt_u2_ex3 src/bt_u2_ex3.cpp)
add_executable(bt_u2_ex4 src/bt_u2_ex4.cpp)

ament_target_dependencies(bt_u2_ex2 rclcpp std_msgs behaviortree_cpp behaviortree_ros2)
ament_target_dependencies(bt_u2_ex3 rclcpp std_msgs behaviortree_cpp behaviortree_ros2)
ament_target_dependencies(bt_u2_ex4 rclcpp std_msgs behaviortree_cpp behaviortree_ros2)


install(TARGETS
  bt_u2_ex2
  bt_u2_ex3
  bt_u2_ex4
  DESTINATION lib/${PROJECT_NAME}
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
