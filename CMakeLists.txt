cmake_minimum_required(VERSION 3.15)
project(wolfsort LANGUAGES C CXX)

add_library(wolfsort INTERFACE)
add_library(wolfsort::wolfsort ALIAS wolfsort)

target_include_directories(wolfsort INTERFACE src)

option(WOLFSORT_BUILD_BENCH "Build benchmark" ON)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
	if (WOLFSORT_BUILD_BENCH)
		add_executable(wolfsort-benchmarks
			src/bench.c
			src/blitsort.h
			src/crumsort.h
			src/quadsort.h
			src/fluxsort.h
			src/gridsort.h
			src/quadsort.h
			src/skipsort.h
			src/wolfsort.h
		)
	endif()
endif()
