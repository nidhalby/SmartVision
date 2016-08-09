

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIR} )
include_directories(${SmartVision_SOURCE_DIR}/common)
include_directories(${SmartVision_SOURCE_DIR}/acquisition)

link_directories(${SmartVision_BINARY_DIR}/common)
add_library(acquisition acquisitionModule.h )

#use libraries of opencv and common
target_link_libraries(acquisition ${OpenCV_LIBS} common)
set_target_properties(acquisition PROPERTIES LINKER_LANGUAGE CXX) 
