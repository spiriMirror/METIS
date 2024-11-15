add_library(metis STATIC)

target_include_directories(metis PUBLIC "${PROJECT_SOURCE_DIR}/include")
target_include_directories(metis PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB metis_sources "${CMAKE_CURRENT_SOURCE_DIR}/*.c")
target_sources(metis PRIVATE ${metis_sources})

target_link_libraries(metis PRIVATE GKlib)

message(STATUS "METIS_IDXTYPEWIDTH: ${METIS_IDXTYPEWIDTH}")
message(STATUS "METIS_REALTYPEWIDTH: ${METIS_REALTYPEWIDTH}")

target_compile_definitions(metis PRIVATE "-DIDXTYPEWIDTH=${METIS_IDXTYPEWIDTH}")
target_compile_definitions(metis PRIVATE "-DREALTYPEWIDTH=${METIS_REALTYPEWIDTH}")