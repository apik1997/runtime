set(SOURCES
    doublemapping.cpp
    dn-u16.cpp
    ${CLR_SRC_NATIVE_DIR}/minipal/debugger.c
    ${CLR_SRC_NATIVE_DIR}/minipal/time.c
)

if(NOT CLR_CROSS_COMPONENTS_BUILD)
    list(APPEND SOURCES
        ${CLR_SRC_NATIVE_DIR}/minipal/cpufeatures.c
    )
endif()

add_library(coreclrminipal
    STATIC
    ${SOURCES}
)

include(${CLR_SRC_NATIVE_DIR}/minipal/configure.cmake)
include_directories(${CMAKE_CURRENT_BINARY_DIR})
