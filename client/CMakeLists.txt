CMAKE_MINIMUM_REQUIRED(VERSION 3.5)
project(client)
set(CMAKE_CXX_STANDARD 20)
file(GLOB SOURCES "src/*.cpp")
file(GLOB_RECURSE HEADERS "include/*.h include/*.hpp")

find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED)

add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} PRIVATE thrift
    ${Boost_LIBRARIES}
    ${OpenCV_LIBS}
)