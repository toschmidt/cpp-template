# Header-Only Library (without source files):
# add_library(<project-name> INTERFACE)
# target_include_directories(<project-name> INTERFACE ${CMAKE_SOURCE_DIR}/src)
# target_link_libraries(<project-name> INTERFACE <dependencies>)

# Static Library (with header files in src/):
# file(GLOB_RECURSE CPP_FILES ${CMAKE_SOURCE_DIR}/src/*.cpp)
# add_library(<project-name> INTERFACE ${CPP_FILES})
# target_include_directories(<project-name> INTERFACE ${CMAKE_SOURCE_DIR}/src)
# target_link_libraries(<project-name> PRIVATE <>)
# target_link_libraries(cpp-benchmark INTERFACE cpp-utility)

# Static Library (with public header files in include/ and private header files in src/)
# file(GLOB_RECURSE CPP_FILES ${CMAKE_SOURCE_DIR}/src/*.cpp)
# add_library(<project-name> STATIC ${CPP_FILES})
# target_include_directories(<project-name
#         PUBLIC $<INSTALL_INTERFACE:include> $<BUILD_INTERFACE:${CMAKE_SOURCE_DIR}/include>
#         PRIVATE ${CMAKE_SOURCE_DIR}/src)
# target_link_libraries(cpp-benchmark INTERFACE <dependencies>)

if (ENABLE_INSTALL)
    include(GNUInstallDirs)

    # Install the project's header files (destination is relative to CMAKE_INSTALL_PREFIX)
    # header-only libraries should keep their header files in the src folder
    # static libraries should have an additional directory (include) to keep the global header files
    # message(STATUS "install_dir=${include_install_dir}")
    # install(
    #         DIRECTORY ${PROJECT_SOURCE_DIR}/src/
    #         DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
    #         FILES_MATCHING PATTERN "*.hpp"
    #)
endif ()
