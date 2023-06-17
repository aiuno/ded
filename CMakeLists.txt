CMAKE_MINIMUM_REQUIRED(VERSION 3.24)
project(ded C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_FLAGS "-Wall -Wextra -pedantic")

if(APPLE)
    set(CMAKE_C_FLAGS ${CMAKE_C_FLAGS} -framework OpenGL)
endif()

include_directories(/usr/include/freetype2)

add_executable(${PROJECT_NAME} src/main.c src/editor.c src/file_browser.c src/common.c src/free_glyph.c src/la.c src/lexer.c src/simple_renderer.c)
target_link_libraries(${PROJECT_NAME} SDL2 GLEW GL freetype m)