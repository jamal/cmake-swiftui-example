cmake_minimum_required(VERSION 3.20)

project(Foobar LANGUAGES Swift)
set(NAME Foobar)

add_executable(${NAME} MACOSX_BUNDLE
    src/ContentView.swift
    src/FoobarApp.swift
)

find_library(SWIFTUI_LIBRARY SwiftUI)
target_link_libraries(${NAME} PRIVATE
    ${SWIFTUI_LIBRARY}
)

set_target_properties(${NAME} PROPERTIES
    MACOSX_BUNDLE_GUI_IDENTIFIER com.example.Foobar
    MACOSX_BUNDLE_BUNDLE_VERSION 1
    MACOSX_BUNDLE_SHORT_VERSION_STRING 1.0
)