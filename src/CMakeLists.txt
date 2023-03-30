file(GLOB_RECURSE PHSRC ${PROJECT_SOURCE_DIR}/src/public/*.h)

add_library(datatypes INTERFACE)
target_include_directories(datatypes INTERFACE
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/src/public>
        $<INSTALL_INTERFACE:include>
        )

install(TARGETS datatypes
        EXPORT ${CMAKE_PROJECT_NAME}Targets
        RUNTIME DESTINATION bin
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
        INCLUDES DESTINATION include
        )

install(FILES ${PHSRC} DESTINATION include)
