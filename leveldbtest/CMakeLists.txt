cmake_minimum_required(VERSION 2.8)
PROJECT(leveldbtest)

include_directories(${CMAKE_CURRENT_SOURCE_DIR} )

  if(STATIC)
    foreach(VAR CMAKE_C_FLAGS_DEBUG CMAKE_CXX_FLAGS_DEBUG CMAKE_C_FLAGS_RELEASE CMAKE_CXX_FLAGS_RELEASE)
      string(REPLACE "/MD" "/MT" ${VAR} "${${VAR}}")
    endforeach()
  endif()

set(SRCS
  main.cpp
  )

set(HDRS
  )

add_executable(leveldbtest ${SRCS} ${HDRS})
target_link_libraries(leveldbtest
      leveldb_static
      )

