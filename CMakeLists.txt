cmake_minimum_required (VERSION 3.12)
project(drbd_cstate VERSION 2.8.0)

set(CPACK_COMPONENTS_ALL ha)
list(APPEND CPACK_COMPONENTS_ALL hadr)
set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cpack)

set(CPACK_GENERATOR RPM DEB)
set(CMAKE_INSTALL_PREFIX "/opt/ha/resource/resources")
SET(CPACK_PACKAGING_INSTALL_PREFIX ${CMAKE_INSTALL_PREFIX})
set(CPACK_RPM_PACKAGE_AUTOREQPROV "no")

set(CPACK_PACKAGE_VERSION "${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}")
set(CPACK_RPM_PACKAGE_RELEASE 14)
set(CPACK_RPM_PACKAGE_LICENSE MIT)
set(CPACK_RPM_PACKAGE_REQUIRES "python >= 2.7.0")
set(CPACK_RPM_CHANGELOG_FILE "${CMAKE_SOURCE_DIR}/changelog.txt")
set(CPACK_PACKAGE_VENDOR "scott yyf")
set(CPACK_RPM_PACKAGE_GROUP "Tony Lip(scott)")
set(CPACK_PACKAGE_CONTACT "yangyingfa@skybility.com")
set(CPACK_RPM_PACKAGE_URL "https://www.skybilityha.com/download/")
set(CPACK_RPM_PACKAGE_DESCRIPTION "Resource to monitor drbd cstate")
set(CPACK_RPM_PACKAGE_ARCHITECTURE "x86_64")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "SkybilityHA drbd cstate monitor resource for skybiltiyha 2.8")
set(CPACK_PACKAGE_NAME "drbd_cstate")

set(CPACK_RPM_COMPONENT_INSTALL ON)
set(CPACK_DEB_COMPONENT_INSTALL ON)

add_subdirectory(drbd_cstate)

include(cpackoption)
include (CPack)