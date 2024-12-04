cmake_minimum_required(VERSION 3.23)

project(ArduinoAvrCore LANGUAGES C CXX ASM)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/cores/arduino)

add_library(arduino_AvrCore STATIC ${ARDUINO_CORE_SOURCES})

target_include_directories(arduino_AvrCore PUBLIC ${CMAKE_CURRENT_LIST_DIR}/cores/arduino)

target_compile_definitions(arduino_AvrCore PUBLIC "ARDUINO=10816")

if(ARDUINO_USB)
    target_compile_definitions(arduino_AvrCore PUBLIC
        USB_VID=${ARDUINO_USB_VID}
        USB_PID=${ARDUINO_USB_PID}
        USB_MANUFACTURER=\"Unknown\"
        USB_PRODUCT=\"${ARDUINO_USB_PRODUCT}\"
    )
endif()

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/libraries/EEPROM)
target_link_libraries(arduino_EEPROM INTERFACE arduino_AvrCore)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/libraries/HID)
target_link_libraries(arduino_HID PUBLIC arduino_AvrCore)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/libraries/SoftwareSerial)
target_link_libraries(arduino_SoftwareSerial PUBLIC arduino_AvrCore)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/libraries/SPI)
target_link_libraries(arduino_SPI PUBLIC arduino_AvrCore)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/libraries/Wire)
target_link_libraries(arduino_Wire PUBLIC arduino_AvrCore)