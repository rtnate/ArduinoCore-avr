cmake_minimum_required(VERSION 3.23)
project(ArduinoLibWire)

add_library(arduino_Wire STATIC src/Wire.cpp src/utility/twi.c)

target_include_directories(arduino_Wire PUBLIC ${CMAKE_CURRENT_LIST_DIR}/src)
