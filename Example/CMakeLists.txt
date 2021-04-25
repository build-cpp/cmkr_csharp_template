# This file was generated automatically by cmkr.

# Create a configure-time dependency on cmake.toml to improve IDE support
if(CMKR_ROOT_PROJECT)
	configure_file(cmake.toml cmake.toml COPYONLY)
endif()

# Target Example
set(Example_SOURCES
	App.xaml.cs
	MainWindow.xaml.cs
	"Properties/AssemblyInfo.cs"
	"Properties/Resources.Designer.cs"
	"Properties/Settings.Designer.cs"
	"Properties/Resources.resx"
	"Properties/Settings.settings"
	App.xaml
	MainWindow.xaml
	App.config
	cmake.toml
)

add_executable(Example ${Example_SOURCES})

get_directory_property(CMKR_VS_STARTUP_PROJECT DIRECTORY ${PROJECT_SOURCE_DIR} DEFINITION VS_STARTUP_PROJECT)
if(NOT CMKR_VS_STARTUP_PROJECT)
	set_property(DIRECTORY ${PROJECT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT Example)
endif()

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${Example_SOURCES})

target_compile_options(Example PRIVATE
	"/langversion:latest"
)

set_target_properties(Example PROPERTIES
	VS_DOTNET_TARGET_FRAMEWORK_VERSION
		v4.6.1
	VS_DOTNET_REFERENCES
		"Microsoft.CSharp;PresentationCore;PresentationFramework;System;System.Core;System.Data;System.Data.DataSetExtensions;System.Net.Http;System.Xaml;System.Xml;System.Xml.Linq;WindowsBase"
)

csharp_set_designer_cs_properties(${Example_SOURCES})
csharp_set_xaml_cs_properties(${Example_SOURCES})
set_property(SOURCE App.xaml PROPERTY VS_XAML_TYPE "ApplicationDefinition")


