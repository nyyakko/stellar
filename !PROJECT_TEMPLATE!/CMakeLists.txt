set(!PROJECT_TEMPLATE!_SourceFiles "")
set(!PROJECT_TEMPLATE!_HeaderFiles "")

add_subdirectory(source)

add_executable(${PROJECT_NAME} ${!PROJECT_TEMPLATE!_SourceFiles} ${!PROJECT_TEMPLATE!_HeaderFiles})

target_include_directories(${PROJECT_NAME} 
    PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include" 
    PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/include/!PROJECT_TEMPLATE!"
)

set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 20)
target_link_libraries(${PROJECT_NAME} PRIVATE ${!PROJECT_TEMPLATE!_ExternalLibraries})