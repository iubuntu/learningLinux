cmake_minimum_required(VERSION 3.10)

project(learningLinux)

add_executable(learningLinux_bin src/learningLinux_bin.c)

install(TARGETS learningLinux_bin DESTINATION bin)
install(FILES "src/learningLinux_text.sh"
    PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE GROUP_READ GROUP_EXECUTE WORLD_READ WORLD_EXECUTE
    DESTINATION bin
    RENAME "learningLinux_text")