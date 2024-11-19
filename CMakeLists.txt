# Copyright (c) Alpaca Core
# SPDX-License-Identifier: MIT
#
cmake_minimum_required(VERSION 3.24 FATAL_ERROR)

project(ac-dict-cocoa
    VERSION 1.0.0
    DESCRIPTION "Converter between ac::Dict and NSDictionary"
    LANGUAGES CXX OBJCXX
)

include(./get-ac-build.cmake)
include(init_ac_prj)

#################
# options

option(AC_DICT_COCOA_BUILD_TESTS "${PROJECT_NAME}: build tests" ${testsDefault})
option(AC_DICT_COCOA_BUILD_EXAMPLES "${PROJECT_NAME}: build examples" ${examplesDefault})
mark_as_advanced(AC_DICT_COCOA_BUILD_TESTS AC_DICT_COCOA_BUILD_EXAMPLES)

#######################################
# packages

include(ac_build_prj_util)

add_ac_local(0.1.1)

#######################################
# subdirs

add_subdirectory(code)

if(AC_DICT_COCOA_BUILD_TESTS)
    enable_testing()
    add_subdirectory(test)
endif()
