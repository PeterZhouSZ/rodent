add_executable(bench_embree
    bench_embree.cpp
    ../../src/driver/obj.h
    ../../src/driver/obj.cpp)
target_include_directories(bench_embree PUBLIC ../common ../../src ${EMBREE_ROOT_DIR}/include ${EMBREE_ROOT_DIR} ${EMBREE_LIBRARY_DIR})
target_compile_definitions(bench_embree PUBLIC ${EMBREE_DEFINITIONS})
target_link_libraries(bench_embree ${EMBREE_DEPENDENCIES} ${AnyDSL_runtime_LIBRARIES})
# Needs the interface file generated by bench_traversal
add_dependencies(bench_embree bench_traversal)
