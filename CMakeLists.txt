# CMAKELISTS TXT

# version
cmake_minimum_required(VERSION 3.10)

# project
project(OpenMesh VERSION 0.1)

# The include files are located in the include directory
include_directories(include)

# this is the file that contains the configuration values
configure_file(include/Config.h.in Config.h)

# load all the files in the src/ folder
file(GLOB SOURCES "src/*.c")

# create an executable
add_executable(OpenMesh ${SOURCES})

# to include the configured file into the project, we use this line
target_include_directories(OpenMesh PUBLIC "${PROJECT_BINARY_DIR}")
