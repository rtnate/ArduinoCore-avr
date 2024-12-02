cmake_minimum_required(VERSION 3.23)
project(ArduinoLibEEPROM)

add_library(arduino_EEPROM INTERFACE)

target_include_directories(arduino_EEPROM INTERFACE ${CMAKE_CURRENT_LIST_DIR}/src)

