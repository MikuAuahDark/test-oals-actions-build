cmake_minimum_required (VERSION 3.1)

project(CMakeVarDump C CXX)

get_cmake_property(_variableNames VARIABLES)
list(SORT _variableNames)
foreach(_variableName ${_variableNames})
	if(_variableName MATCHES "^CMAKE_VS_")
		message(STATUS "${_variableName}=${${_variableName}}")
	endif()
endforeach()

add_executable(hello0 hello.c)
add_executable(hello1 hello.cpp)
