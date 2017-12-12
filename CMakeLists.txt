
cmake_minimum_required(VERSION 3.6)

project(demangler CXX)

# Set the default build type to 'Release'
if (NOT CMAKE_BUILD_TYPE)	
	set(default_build_type "Release")
	message(STATUS "Setting build type to '${default_build_type}' as none was specified.")
	set(CMAKE_BUILD_TYPE "${default_build_type}" CACHE STRING "Choose the type of build." FORCE)
endif()

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/lib")

option(DEMANGLER_DOC "Build public API documentation (requires Doxygen)." OFF)
option(DEMANGLER_TOOLS "Build tools." OFF)
option(DEMANGLER_TESTS "Build tests." OFF)

add_subdirectory(deps)
if(DEMANGLER_DOC)
	add_subdirectory(doc)
endif()
add_subdirectory(src)
if(DEMANGLER_TESTS)
	add_subdirectory(tests)
endif()
