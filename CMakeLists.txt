cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello VERSION 1.0)

# Where to find source file
file(GLOB_RECURSE SRC_FILES src/*.cpp)

# Where to find binary files
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)

# Create executable
add_executable(hello main.cpp ${SRC_FILES})

# Link libraries with executable
target_link_libraries(hello sfml-graphics sfml-window sfml-system)

# Where to find the headers
target_include_directories(hello PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)



# Depending on external library
# find_package(SFML 2.6 REQUIRED network audio graphics window system)
# target_include_directories(hello PUBLIC ${SFML_INCLUDE_DIR})
# target_link_libraries(hello PUBLIC ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})



