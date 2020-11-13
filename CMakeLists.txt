cmake_minimum_required(VERSION 3.17)

project(cppwebsockets)

set(CMAKE_CXX_STANDARD 17) 

add_definitions(-DLWS_NO_EXTENSIONS)
set(OPENSSL_INCLUDE_DIR /usr/local/Cellar/openssl@1.1/1.1.1h/include)
set(LIBS ssl websockets)
set(LIB_DIRS /usr/local/lib /usr/local/opt/openssl/lib)

add_library(cppwebsockets
    Util.cpp Util.h
    WebSocketServer.cpp WebSocketServer.h
)

target_include_directories(cppwebsockets PUBLIC /usr/local/include ${OPENSSL_INCLUDE_DIR})
