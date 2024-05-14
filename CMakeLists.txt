cmake_minimum_required(VERSION 3.10)

project(learningLinux VERSION 1.0 DESCRIPTION "Package built example")

add_executable(learningLinux_bin src/learningLinux_bin.c)

install(TARGETS learningLinux_bin DESTINATION bin)
install(FILES "src/learningLinux_text.sh"
    PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE
    DESTINATION bin
    RENAME "learningLinux_text")

set(CPACK_PACKAGE_VENDOR "long beach")
set(CPACK_RPM_PACKAGE_LICENSE "BSD")
set(CPACK_PACKAGE_VERSION ${CMAKE_PROJECT_VERSION})
set(CPACK_GENERATOR "RPM")
set(CPACK_PACKAGE_NAME "learningLinux")
set(CPACK_RPM_FILE_NAME "RPM-DEFAULT")
set(CPACK_RPM_PACKAGE_RELEASE_DIST ON)
include(CPack)