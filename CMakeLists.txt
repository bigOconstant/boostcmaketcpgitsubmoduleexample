
#FIND_PACKAGE( Boost 1.67 COMPONENTS program_options REQUIRED )

cmake_minimum_required(VERSION 3.0)
SET(CMAKE_CXX_STANDARD 17)


project(boostexperiment)
SET(CMAKE_CXX_FLAGS -lboost_system)



find_package(Boost 1.67 COMPONENTS program_options REQUIRED)

  
find_package(Boost REQUIRED COMPONENTS system thread)

INCLUDE_DIRECTORIES( ${Boost_INCLUDE_DIR} )

add_executable(boostexperiment main.cpp)

target_link_libraries( boostexperiment  LINK_PUBLIC ${Boost_LIBRARIES})


install(TARGETS boostexperiment RUNTIME DESTINATION bin)
