cmake_minimum_required(VERSION 2.8)
project(GB28181_RTMP)


#file(GLOB Third_Include "thirdparty/include/*.h++"
#  "thirdparty/include/glog/*.h"
#  "thirdparty/include/jrtlib3/*.h"
#  "thirdparty/include/osip/*.h"
#  ""
#  )

set(libPath ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/lib)
link_directories(${libPath})

include_directories("thirdparty/include"
  "thirdparty/include/osip"
  "thirdparty/include/mxml"
  "thirdparty/include/pugixml"
  "thirdparty/include/jrtplib3"
  "thirdparty/include/ffmpeg"
  "thirdparty"
  "include"
  )

FILE(GLOB INCLUDE "include/*.h")
FILE(GLOB SRC "src/*.cpp")
FILE(GLOB LIBS "thirdparty/lib/*.lib")

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
message(STATUS "ThirdParty Include: ${Third_Include}")
message(STATUS "Include: ${INCLUDE}")
message(STATUS "Src: ${SRC}")

add_executable(gb28181_rtmp_exe ${SRC} ${INCLUDE})
# target_link_directories(gb28181_rtmp_exe "thirdparty/lib")
# target_link_libraries(gb28181_rtmp_exe ${LIBS})
