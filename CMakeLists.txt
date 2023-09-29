cmake_minimum_required(VERSION 3.20)
project(testapp LANGUAGES CXX)

find_package(Qt6 COMPONENTS Core Gui Widgets ShaderTools)

qt_add_executable(testapp
    main.cpp
)

target_link_libraries(testapp PRIVATE
    Qt::Core
    Qt::Gui
    Qt::GuiPrivate
    Qt::Widgets
)

qt_add_shaders(testapp "shaders"
    PREFIX
        "/shaders"
    FILES
        "color.vert"
        "color.frag"
)
