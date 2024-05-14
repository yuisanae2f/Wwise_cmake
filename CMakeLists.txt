cmake_minimum_required(VERSION 3.22)
project(audioKineticTest)

set(WWISE_SDK_DIR $ENV{WWISESDK})
set(LIB_DIRS ${CMAKE_CURRENT_SOURCE_DIR}/Release/lib ${WWISE_SDK_DIR}/x64_vc170/Release/lib)

file(GLOB LIB_FILES ${LIB_DIRS}/*.lib)

add_library(${PROJECT_NAME} ./a.c)

target_include_directories(
	${PROJECT_NAME} PUBLIC
	${WWISE_SDK_DIR}/include
)

target_link_libraries(
	${PROJECT_NAME} PRIVATE
	${LIB_FILES}
)