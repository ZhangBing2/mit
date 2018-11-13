# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.11)

project ("mit")
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

# Include sub-projects.
add_subdirectory ("Algorithms6.006")
add_subdirectory ("Algorithms6.046")
set_property( DIRECTORY PROPERTY VS_STARTUP_PROJECT "Algorithms6.006" )

