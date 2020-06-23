cmake_minimum_required(VERSION 3.0)

SET(CMAKE_CXX_STANDARD 20)
project(tcpserver)

find_package(Boost 1.72 COMPONENTS program_options REQUIRED)
find_package(Boost REQUIRED COMPONENTS system thread)

INCLUDE_DIRECTORIES( ${Boost_INCLUDE_DIR} )
set( project_sources
   main.cpp
   tcp_connection.cpp
)

add_executable(${PROJECT_NAME}
  ${project_sources}
)
add_subdirectory(libs/librdkafka)

target_link_libraries( tcpserver  LINK_PUBLIC rdkafka ${Boost_LIBRARIES} )


install(TARGETS tcpserver RUNTIME DESTINATION bin)