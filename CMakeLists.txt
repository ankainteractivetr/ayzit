cmake_minimum_required(VERSION 4.0.3) 

project(Ayzit 
        VERSION      1.0.0
        DESCRIPTION  "A Freeware 3D Graphics Viewer"
        HOMEPAGE_URL "https://www.ankainteractive.com/#ayzit"
        LANGUAGES    CXX) 

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_definitions(-DUNICODE -D_UNICODE)

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /O2 /Ob2 /Ot /GL /TP")

string(REGEX REPLACE "/RTC(su|[1su])" "" CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE}")

set(CMAKE_EXE_LINKER_FLAGS_RELEASE "${CMAKE_EXE_LINKER_FLAGS_RELEASE} /SUBSYSTEM:WINDOWS")

set(SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/source)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

add_executable(${PROJECT_NAME} WIN32)

add_subdirectory(source)

