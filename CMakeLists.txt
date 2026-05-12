cmake_minimum_required(VERSION 3.10)
project(MyImGuiProject)

set(SOURCES 
    main.cpp
    imgui.cpp
    imgui_draw.cpp
    imgui_widgets.cpp
    imgui_tables.cpp
    imgui_impl_dx11.cpp
    imgui_impl_win32.cpp
)

add_executable(MyGuiApp ${SOURCES})

target_link_libraries(MyGuiApp PRIVATE 
    d3d11 
    d3dcompiler 
    dwmapi
    mingw32 
    -mwindows
    -static-libgcc
    -static-libstdc++
    -Wl,-Bstatic,--whole-archive -lwinpthread -Wl,--no-whole-archive
)