cmake_minimum_required (VERSION 3.1)

project(CMakeVarDump C CXX)

message(STATUS "CMAKE_SYSTEM_PROCESSOR=${CMAKE_SYSTEM_PROCESSOR}")
if(CMAKE_VS_PLATFORM_NAME STREQUAL "ARM64")
	message(STATUS "BOO")
endif()
if(MSVC)
	message(STATUS "MSVC_CXX_ARCHITECTURE_ID=${MSVC_CXX_ARCHITECTURE_ID}")
endif()
get_cmake_property(_variableNames VARIABLES)
list(SORT _variableNames)
foreach(_variableName ${_variableNames})
	if(_variableName MATCHES "^CMAKE_VS_")
		message(STATUS "${_variableName}=${${_variableName}}")
	endif()
endforeach()

add_executable(hello0 hello.c)
add_executable(hello1 hello.cpp)
