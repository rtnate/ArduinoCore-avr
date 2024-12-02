cmake_minimum_required(VERSION 3.23)
project(ArduinoLibSoftwareSerial)

add_library(arduino_SoftwareSerial STATIC src/SoftwareSerial.cpp)

target_include_directories(arduino_SoftwareSerial PUBLIC ${CMAKE_CURRENT_LIST_DIR}/src)
