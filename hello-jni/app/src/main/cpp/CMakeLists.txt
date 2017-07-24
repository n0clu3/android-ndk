cmake_minimum_required(VERSION 3.4.1)

include("../../../../cotire/cotire.cmake")

add_library(hello-jni SHARED
            hello-jni.c)

cotire("hello-jni")
set_target_properties("hello-jni" PROPERTIES EXCLUDE_FROM_ALL 1 EXCLUDE_FROM_DEFAULT_BUILD 1)
set_target_properties("hello-jni_unity" PROPERTIES EXCLUDE_FROM_ALL 0 EXCLUDE_FROM_DEFAULT_BUILD 0)

# Include libraries needed for hello-jni lib
target_link_libraries(hello-jni
                      android
                      log)
