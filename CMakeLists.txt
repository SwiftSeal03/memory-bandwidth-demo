set(TARGET_NAME memory_profiler)
add_executable(${TARGET_NAME} main.c functions.c monotonic_timer.c)

target_compile_options(memory_profiler PRIVATE -Ofast -march=native)
find_package(OpenMP REQUIRED)
if (OpenMP_C_FOUND)
  target_link_libraries(memory_profiler PUBLIC OpenMP::OpenMP_C)
endif()
