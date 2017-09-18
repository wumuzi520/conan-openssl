PROJECT(MyHello)
cmake_minimum_required(VERSION 2.8)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
CONAN_BASIC_SETUP()

find_package(OpenSSL)

IF(NOT OPENSSL_FOUND)
    # Test only if found, ws32 etc not linked here
    MESSAGE(FATAL_ERROR "ERROR! OPENSSL NOT FOUND!")
ENDIF()


ADD_EXECUTABLE(md5 md5.cpp)
TARGET_LINK_LIBRARIES(md5 ${CONAN_LIBS})