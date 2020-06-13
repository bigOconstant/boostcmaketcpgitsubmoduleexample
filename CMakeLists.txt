cmake_minimum_required(VERSION 3.0)

project(boostexperiment)

add_executable(boostexperiment main.cpp)

install(TARGETS boostexperiment RUNTIME DESTINATION bin)
