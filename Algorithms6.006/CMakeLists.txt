# CMakeList.txt : CMake project for Leetcode, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.10)

# Add source to this project's executable.
project ("Algorithms6.006")
SET(CMAKE_INCLUDE_CURRENT_DIR ON)

if (MSVC_VERSION GREATER_EQUAL "1900")
    include(CheckCXXCompilerFlag)
    CHECK_CXX_COMPILER_FLAG("/std:c++latest" _cpp_latest_flag_supported)
    if (_cpp_latest_flag_supported)
        add_compile_options("/std:c++latest")
	else ()
		set (CMAKE_CXX_STANDARD 17)
		set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++17")
    endif()
endif()

