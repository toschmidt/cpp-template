# Header-Only Library (without source files):
# add_library(<project-name> INTERFACE)
# target_include_directories(<project-name> INTERFACE ${CMAKE_CURRENT_LIST_DIR})
# target_link_libraries(<project-name> INTERFACE <dependencies>)

# Static Library (with source files):
# file(GLOB_RECURSE CPP_FILES ${CMAKE_CURRENT_LIST_DIR}/*.cpp)
# add_library(<project-name> INTERFACE ${CPP_FILES})
# target_link_directories(<project-name> INTERFACE ${CMAKE_CURRENT_LIST_DIR})
# target_link_libraries(<project-name> PRIVATE <dependencies>)

# For more information on library definitions in cmake see https://pabloariasal.github.io/2018/02/19/its-time-to-do-cmake-right/

