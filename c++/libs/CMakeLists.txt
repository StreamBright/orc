# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
# 
#     http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

if (CMAKE_CXX_COMPILER_ID STREQUAL "Clang")
  if (NOT CMAKE_C_COMPILER_VERSION STREQUAL "" AND
      NOT CMAKE_C_COMPILER_VERSION VERSION_LESS "4.0")
    set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-shift-negative-value")
  endif ()
  set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-deprecated-declarations")
endif ()

add_subdirectory(gmock-${GMOCK_VERSION})
add_subdirectory(zlib-${ZLIB_VERSION})
add_subdirectory(protobuf-${PROTOBUF_VERSION})
add_subdirectory(snappy-${SNAPPY_VERSION})
add_subdirectory(lz4-${LZ4_VERSION})
