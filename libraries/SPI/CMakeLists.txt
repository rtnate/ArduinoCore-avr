cmake_minimum_required(VERSION 3.23)
project(ArduinoLibSPI)

add_library(arduino_SPI STATIC src/SPI.cpp)

target_include_directories(arduino_SPI PUBLIC ${CMAKE_CURRENT_LIST_DIR}/src)
