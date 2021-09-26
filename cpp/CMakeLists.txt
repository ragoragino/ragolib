CMAKE_MINIMUM_REQUIRED(VERSION 3.10 FATAL_ERROR)

ADD_LIBRARY(ragolibcpp STATIC 
    "logger.cpp")

TARGET_COMPILE_FEATURES(ragolibcpp PUBLIC cxx_std_17)
TARGET_INCLUDE_DIRECTORIES(ragolibcpp PUBLIC  
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>  
    $<INSTALL_INTERFACE:include/ragolibcpp>
)

INSTALL(FILES "logger.hpp" DESTINATION include/ragolibcpp)
INSTALL(TARGETS ragolibcpp EXPORT ragolibcpp-targets DESTINATION lib/ragolibcpp)
INSTALL(EXPORT ragolibcpp-targets DESTINATION lib/ragolibcpp)
INSTALL(FILES ragolibcpp-config.cmake DESTINATION lib/ragolibcpp)