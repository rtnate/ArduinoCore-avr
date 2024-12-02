cmake_minimum_required(VERSION 3.23)
project(ArduinoLibHID)

add_library(arduino_HID STATIC src/HID.cpp)

target_include_directories(arduino_HID PUBLIC ${CMAKE_CURRENT_LIST_DIR}/src)
