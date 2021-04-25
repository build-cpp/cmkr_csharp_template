# This file was generated automatically by cmkr.

# Create a configure-time dependency on cmake.toml to improve IDE support
if(CMKR_ROOT_PROJECT)
	configure_file(cmake.toml cmake.toml COPYONLY)
endif()

# Target WindowsFormsApp
set(WindowsFormsApp_SOURCES
	Form1.Designer.cs
	Form1.cs
	Program.cs
	"Properties/AssemblyInfo.cs"
	"Properties/Resources.Designer.cs"
	"Properties/Settings.Designer.cs"
	"Properties/Resources.resx"
	"Properties/Settings.settings"
	App.config
	cmake.toml
)

add_executable(WindowsFormsApp ${WindowsFormsApp_SOURCES})

get_directory_property(CMKR_VS_STARTUP_PROJECT DIRECTORY ${PROJECT_SOURCE_DIR} DEFINITION VS_STARTUP_PROJECT)
if(NOT CMKR_VS_STARTUP_PROJECT)
	set_property(DIRECTORY ${PROJECT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT WindowsFormsApp)
endif()

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${WindowsFormsApp_SOURCES})

target_compile_options(WindowsFormsApp PRIVATE
	"/langversion:latest"
)

set_target_properties(WindowsFormsApp PROPERTIES
	VS_DOTNET_TARGET_FRAMEWORK_VERSION
		v4.6.1
	VS_DOTNET_REFERENCES
		"Microsoft.CSharp;System;System.Core;System.Data;System.Drawing;System.Windows.Forms"
)

csharp_set_windows_forms_properties(${WindowsFormsApp_SOURCES})


