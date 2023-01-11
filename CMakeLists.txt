# The following four lines of boilerplate have to be in your project's CMakeLists
# in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)
set(EXTRA_COMPONENT_DIRS "<add your project folder path here>/components/bytebeam_esp_sdk") 
#example - set(EXTRA_COMPONENT_DIRS "C:/bytebeam/ESP_DHT11_Bytebeam/components/bytebeam_esp_sdk") 
# (Not part of the boilerplate)
# This example uses an extra component for common functions such as Wi-Fi and Ethernet connection.
set(EXTRA_COMPONENT_DIRS $ENV{IDF_PATH}/examples/common_components/protocol_examples_common
                         ../components)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(bytebeam_example_app)

