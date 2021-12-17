# Adding new variable 
SET(UITLS_LIB_SRC 
    computeTime.cpp 
    logger.cpp
    plotting.cpp
    )

# Creating the utils library where we add all the source files included in our library
add_library(UTILS ${UITLS_LIB_SRC})

## Compiler can find the included files for our library
# Fun allows the main project to detect all header files    
target_include_directories(Utils PUBLIC ${CMAKE CURRENT SOURCE DIR})


