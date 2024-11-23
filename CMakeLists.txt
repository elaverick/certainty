cmake_minimum_required(VERSION 3.10) # Adjust version as needed
project(CertaintyApp)

# Define the tvision paths (can also be passed as variables during configuration)
set(TVISION_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/third_party/tvision/include" CACHE PATH "Path to tvision include directory")
set(TVISION_LIBRARY "${CMAKE_SOURCE_DIR}/third_party/tvision/lib/libtvision.a" CACHE FILEPATH "Path to tvision library")

# Include the tvision header files
include_directories(${TVISION_INCLUDE_DIR})

# Specify the target executable
add_executable(certainty src/main.cpp)

# Link the tvision library and other required libraries
target_link_libraries(certainty PRIVATE ${TVISION_LIBRARY} ncursesw gpm)
