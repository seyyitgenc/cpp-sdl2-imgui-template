cmake_minimum_required(VERSION 3.0.0)

project(sdl-imgui)

find_package(SDL2 REQUIRED)

set(sources
main.cpp

imgui/imconfig.h
imgui/imgui.h
imgui/imgui.cpp
imgui/imgui_internal.h
imgui/imstb_rectpack.h
imgui/imstb_textedit.h
imgui/imstb_truetype.h
imgui/imgui_demo.cpp
imgui/imgui_draw.cpp
imgui/imgui_tables.cpp
imgui/imgui_widgets.cpp

#to make it work imgui with sdl2 and sdl2-renderer these files must be included
imgui/imgui_impl_sdl2.cpp
imgui/imgui_impl_sdl2.h
imgui/imgui_impl_sdlrenderer.h
imgui/imgui_impl_sdlrenderer.cpp

)

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

add_executable(sdl-imgui ${sources})
target_link_libraries(sdl-imgui ${SDL2_LIBRARIES})