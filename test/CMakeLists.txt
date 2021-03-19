if (ENABLE_TESTING)

    file(GLOB_RECURSE TESTER_CPP_FILES ${CMAKE_CURRENT_LIST_DIR}/*.cpp)
    file(GLOB_RECURSE TESTER_HPP_FILES ${CMAKE_CURRENT_LIST_DIR}/*.hpp)

    add_executable(tester ${TESTER_CPP_FILES} ${TESTER_HPP_FILES})

    # Link the tester with the project's library
    # target_link_libraries(tester PRIVATE <project-name>)

    # Link with the test framework:
    # Catch2:
    # target_link_libraries(tester PRIVATE catch2 threads)

endif ()
