cmake_minimum_required(VERSION 3.18)
project(imgui)

add_library(${PROJECT_NAME}
    imgui.cpp
    
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp

    backends/imgui_impl_opengl3.cpp
    backends/imgui_impl_glfw.cpp
)

target_include_directories(${PROJECT_NAME}
    PUBLIC
        .

    PRIVATE
        ../glfw/include
)