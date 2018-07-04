cmake_minimum_required(VERSION 3.10)
project(hotspot)
include_directories(
        src/share/vm
        src/os/linux/vm
        src/cpu/x86/vm
        src/os_cpu/linux_x86/vm
        src/share/vm/precompiled
        src/share/vm/utilities)
file(GLOB_RECURSE SOURCE_FILES "*.cpp" "*.hpp" "*.c" "*.h")
add_executable(hotspot ${SOURCE_FILES})
add_definitions(-DTARGET_COMPILER_gcc -DLINUX -DTARGET_ARCH_x86 -DTARGET_OS_FAMILY_linux)

add_definitions(-DTASKQUEUE_STATS)
#set(VALUE_OBJ_CLASS_SPEC ValueObj)