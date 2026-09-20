cmake_minimum_required(VERSION 3.8)
project(sim_pkg)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
install(PROGRAMS launch/sim_launch.py
  DESTINATION lib/${PROJECT_NAME}
)

INSTALL(DIRECTORY urdfs/
  DESTINATION share/${PROJECT_NAME}/urdfs
)
install(DIRECTORY meshes/
  DESTINATION share/${PROJECT_NAME}/meshes
)
install(DIRECTORY launch/
  DESTINATION share/${PROJECT_NAME}/launch
)
install(DIRECTORY config/
  DESTINATION share/${PROJECT_NAME}/config
)
install(DIRECTORY worlds/
  DESTINATION share/${PROJECT_NAME}/worlds
)
ament_package()
