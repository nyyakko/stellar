set(stellar_SourceFiles "")
set(stellar_HeaderFiles "")

add_subdirectory(source)

add_executable(${PROJECT_NAME} ${stellar_SourceFiles} ${stellar_HeaderFiles})

target_include_directories(${PROJECT_NAME} 
    PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include" 
    PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/include/stellar"
)

set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 20)
target_link_libraries(${PROJECT_NAME} PRIVATE ${stellar_ExternalLibraries})