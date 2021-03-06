cmake_minimum_required (VERSION 2.6)

project ("libcoderwall")

# Define the source and binary dirs of coderwall.
set(CODERWALL_SOURCE_DIR ${PROJECT_SOURCE_DIR})
set(CODERWALL_BINARY_DIR ${PROJECT_BINARY_DIR})

set (CODERWALL_VENDORS_SOURCE_DIR "${PROJECT_SOURCE_DIR}/vendor")
set (CODERWALL_VENDORS_BINARY_DIR "${PROJECT_BINARY_DIR}/vendor")

set (CODERWALL_CURL_DIR  "${CODERWALL_VENDORS_SOURCE_DIR}/curl-7.25.0")
set (CODERWALL_YAJL_DIR  "${CODERWALL_VENDORS_SOURCE_DIR}/yajl-2.0.1")
set (CODERWALL_GTEST_DIR "${CODERWALL_VENDORS_SOURCE_DIR}/gtest-1.6.0")

add_subdirectory (${CODERWALL_CURL_DIR}  "${CODERWALL_VENDORS_BINARY_DIR}/curl")
add_subdirectory (${CODERWALL_YAJL_DIR}  "${CODERWALL_VENDORS_BINARY_DIR}/yajl")
add_subdirectory (${CODERWALL_GTEST_DIR} "${CODERWALL_VENDORS_BINARY_DIR}/gtest" EXCLUDE_FROM_ALL)

add_subdirectory ("${PROJECT_SOURCE_DIR}/lib")
add_subdirectory ("${PROJECT_SOURCE_DIR}/example" EXCLUDE_FROM_ALL)
add_subdirectory ("${PROJECT_SOURCE_DIR}/tests" EXCLUDE_FROM_ALL)
