set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

include_directories(
  ${CMAKE_CURRENT_BINARY_DIR}
)
include(${CMAKE_CURRENT_SOURCE_DIR}/header-deps.cmake)

file(GLOB SRC_FILES src/*.cpp)
file(GLOB HEADER_FILES include/*.h)

add_library(BifrostLib
  SHARED
  ${SRC_FILES}
  ${HEADER_FILES}
)
