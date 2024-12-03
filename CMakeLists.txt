cmake_minimum_required(VERSION 3.31)

project(imgui)

set(IMGUI_INCLUDES
    imgui.h
    backends/imgui_impl_glfw.h
    backends/imgui_impl_opengl3.h
)

set(IMGUI_SOURCES
    imgui.cpp
    backends/imgui_impl_glfw.cpp
    backends/imgui_impl_opengl3.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
)

add_library(imgui STATIC
    ${IMGUI_INCLUDES}
    ${IMGUI_SOURCES}
)

target_include_directories(imgui PUBLIC /)
target_include_directories(imgui PUBLIC imgui)

target_link_libraries(imgui PRIVATE glad glfw)
