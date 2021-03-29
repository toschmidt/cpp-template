if (ENABLE_BENCHMARKING)

    # header only library to link the generated benchmarks with
    add_library(benchmark_lib INTERFACE)
    target_include_directories(benchmark_lib INTERFACE ${CMAKE_SOURCE_DIR}/benchmark)

    # generate benchmarks from json files, will return a list of executables in BENCHMARKS
    generate_benchmarks_from_folder(${CMAKE_SOURCE_DIR}/benchmark BENCHMARKS)

    # link each benchmark with the requirede libs
    foreach (target ${BENCHMARKS})
        target_link_libraries(${target} PRIVATE benchmark_lib)
        # target_link_libraries(${target} PRIVATE <project-name>)
        # target_link_libraries(${target} PRIVATE cpp-benchmark googlebenchmark threads cpp-utility)
        # cpp-benchmark depends on googlebenchmark, threads and cpp-utility
    endforeach ()

endif ()
