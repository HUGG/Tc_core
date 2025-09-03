cmake_minimum_required(VERSION 3.10)

# set the project name
project(RDAAM_He)

# add the executable
add_executable(RDAAM_He RDAAM.cpp RDAAM_He.cpp)

# define link options
target_link_options(RDAAM_He PRIVATE -static-libstdc++)
