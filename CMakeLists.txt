cmake_minimum_required (VERSION 3.0)

# Cmake min version
cmake_policy(SET CMP0012 NEW)

# Project name defined
project (Chapter2) 

#Find Package
FIND_PACKAGE( OpenCV 4.0.0 REQUIRED)

#SHOW VERSION

MESSAGE("OPENCV version: ${OPENCV_VERSION}")

## # Add OpenCV header files to project
#Add path to the include directories/header files to the environ
include_directories(${OPENCV_INCLUDE_DIR})


#Add the path to the complied directories to the environ
link_directories(${OPENCV_LIB_DIR}) 

# Add a subdirectory to the build. 
    add_subdirectory(utils)

# Add optional log with a precompiler definition 
    option(WITH_LOG "Build with output logs and images in tmp" OFF) 
    if(WITH_LOG) 
       add_definitions(-DLOG) 
    endif(WITH_LOG)

# Create a variable called SRC 
    SET(SRC main.cpp) 

# Create our executable 
    ADD_EXECUTABLE(${PROJECT_NAME} ${SRC}) 

# Link our library, creates a executable and links to the OpenCV
    TARGET_LINK_LIBRARIES(${PROJECT_NAME} ${OpenCV_LIBS} utils) 



