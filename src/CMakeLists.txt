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

    # Install a header-only library (destination is relative to CMAKE_INSTALL_PREFIX)
    # header-only libraries keep their header files in the src folder
    # install(DIRECTORY ${PROJECT_SOURCE_DIR}/src/
    #         DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})

    # Install a static libraries (destination is relative to CMAKE_INSTALL_PREFIX)
    # static libraries should have an additional directory (include) for the global header files
    # install(DIRECTORY ${PROJECT_SOURCE_DIR}/src/
    #         DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
    # install(TARGETS <project-name>
    #         LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR})
endif ()
