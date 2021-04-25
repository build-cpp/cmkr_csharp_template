# This file was generated automatically by cmkr.

cmake_minimum_required(VERSION 3.15)

# Regenerate CMakeLists.txt automatically in the root project
set(CMKR_ROOT_PROJECT OFF)
if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
	set(CMKR_ROOT_PROJECT ON)

	# Bootstrap cmkr
	include(cmkr.cmake OPTIONAL RESULT_VARIABLE CMKR_INCLUDE_RESULT)
	if(CMKR_INCLUDE_RESULT)
		cmkr()
	endif()

	# Enable folder support
	set_property(GLOBAL PROPERTY USE_FOLDERS ON)
endif()

# Create a configure-time dependency on cmake.toml to improve IDE support
if(CMKR_ROOT_PROJECT)
	configure_file(cmake.toml cmake.toml COPYONLY)
endif()

project(cmkr_csharp_template
	LANGUAGES
		CSharp
	VERSION
		0.1.0
)

include(CSharpUtilities)

# Example
set(CMKR_CMAKE_FOLDER ${CMAKE_FOLDER})
if(CMAKE_FOLDER)
	set(CMAKE_FOLDER "${CMAKE_FOLDER}/Example")
else()
	set(CMAKE_FOLDER Example)
endif()
add_subdirectory(Example)
set(CMAKE_FOLDER ${CMKR_CMAKE_FOLDER})

# WindowsFormsApp
set(CMKR_CMAKE_FOLDER ${CMAKE_FOLDER})
if(CMAKE_FOLDER)
	set(CMAKE_FOLDER "${CMAKE_FOLDER}/WindowsFormsApp")
else()
	set(CMAKE_FOLDER WindowsFormsApp)
endif()
add_subdirectory(WindowsFormsApp)
set(CMAKE_FOLDER ${CMKR_CMAKE_FOLDER})


