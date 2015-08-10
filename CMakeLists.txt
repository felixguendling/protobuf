project(protobuf)
cmake_minimum_required(VERSION 2.6)

include_directories(.)
include_directories(src)

if (NOT MSVC)
  set(PROTOBUF_COMPILE_FLAGS "-std=c++1y -DHAVE_PTHREAD")
endif()

add_library(libprotobuf-cpp-lite STATIC
    src/google/protobuf/stubs/common.cc
    src/google/protobuf/stubs/once.cc
    src/google/protobuf/extension_set.cc
    src/google/protobuf/generated_message_util.cc
    src/google/protobuf/message_lite.cc
    src/google/protobuf/repeated_field.cc
    src/google/protobuf/wire_format_lite.cc
    src/google/protobuf/io/coded_stream.cc
    src/google/protobuf/io/zero_copy_stream.cc
    src/google/protobuf/io/zero_copy_stream_impl_lite.cc
)
set_target_properties(libprotobuf-cpp-lite PROPERTIES COMPILE_FLAGS ${PROTOBUF_COMPILE_FLAGS})
