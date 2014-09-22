set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

include_directories(
  ${CMAKE_CURRENT_BINARY_DIR}
)
include(${CMAKE_CURRENT_SOURCE_DIR}/header-deps.cmake)

get_property(dirs DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY INCLUDE_DIRECTORIES)
foreach(dir ${dirs})
  message(STATUS "dir='${dir}'")
endforeach()

file(GLOB SRC_FILES src/*.cpp)
file(GLOB HEADER_FILES include/*.h include/*.hpp)

add_executable(BifrostTests
  ${SRC_FILES}
  ${HEADER_FILES}
)

add_dependencies(BifrostTests BifrostLib)

target_link_libraries(BifrostTests BifrostLib)
