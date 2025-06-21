cmake_minimum_required(VERSION 3.10)
project(TicTacToe)

option(BUILD_SHARED_LIBS "Build as a shared library" OFF)

add_library(tictactoe_lib STATIC
    include/board.hpp
    include/game.hpp
    include/moves.hpp
    include/tictactoe.hpp
    src/board.cpp
    src/game.cpp
    src/moves.cpp
)

target_include_directories(tictactoe_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(tictactoe src/main.cpp)
target_link_libraries(tictactoe PRIVATE tictactoe_lib)