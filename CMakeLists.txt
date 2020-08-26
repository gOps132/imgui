# imgui test for link testing

cmake_minimum_required(VERSION 3.14)
project(imgui-test
    LANGUAGES CXX
)

option(IMGUI_DEMO "Include the ImGui demo window implementation in library" ON)
message("no examples, use imgui-cmake submodule")

set(IMGUI_SOURCES
    imgui.cpp
    imgui_draw.cpp
    imgui_widgets.cpp
    $<$<BOOL:${IMGUI_DEMO}>:imgui_demo.cpp>
)

add_library(${PROJECT_NAME} STATIC ${IMGUI_SOURCES})

target_include_directories(${PROJECT_NAME} 
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
)