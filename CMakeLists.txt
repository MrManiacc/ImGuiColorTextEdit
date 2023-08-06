cmake_minimum_required(VERSION 3.25)

project(ImGuiColorTextEdit)

set(CMAKE_CXX_STANDARD 23)
set(BOOST_REGEX_STANDALONE ON)
add_subdirectory(vendor/regex)

add_library(ImGuiColorTextEdit STATIC
        TextEditor.cpp
        TextEditor.h
        ImGuiDebugPanel.cpp
        LanguageDefinitions.cpp)

message(STATUS "ImGuiColorTextEdit: ${CMAKE_CURRENT_SOURCE_DIR}")

target_include_directories(ImGuiColorTextEdit PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(ImGuiColorTextEdit PUBLIC Boost::regex imgui)