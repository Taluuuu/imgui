cmake_minimum_required(VERSION 3.18)

set(IMGUI_SOURCES
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp)

if(IMGUI_USE_OPENGL)
    list(APPEND IMGUI_SOURCES
        backends/imgui_impl_opengl3.cpp)
endif()

if(IMGUI_USE_GLFW)
    list(APPEND IMGUI_SOURCES
        backends/imgui_impl_glfw.cpp)
endif()

add_library(imgui ${IMGUI_SOURCES})

target_include_directories(imgui
    PUBLIC
        .
    PRIVATE
        ../glfw/include/)