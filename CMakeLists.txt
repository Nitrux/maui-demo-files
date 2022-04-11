# Copyright 2018-2020 Camilo Higuita <milo.h@aol.com>
# Copyright 2018-2020 Nitrux Latinoamericana S.C.
#
# SPDX-License-Identifier: GPL-3.0-or-later

cmake_minimum_required(VERSION 3.16)

set(MAUI_DEMO_FILES_VERSION 1.0.0)

project(maui_demo_files VERSION ${MAUI_DEMO_FILES_VERSION})

find_package(ECM ${REQUIRED_KF5_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake" ${ECM_MODULE_PATH})

if(UNIX AND NOT APPLE AND NOT ANDROID)
    include(KDEInstallDirs)
    include(KDECMakeSettings)
endif()

include(FeatureSummary)

install(DIRECTORY Music/ DESTINATION $ENV{HOME}/Music)
install(DIRECTORY Videos/ DESTINATION $ENV{HOME}/Videos)
install(DIRECTORY Pictures/ DESTINATION $ENV{HOME}/Pictures)
install(DIRECTORY Documents/ DESTINATION $ENV{HOME}/Documents)
install(DIRECTORY Downloads/ DESTINATION $ENV{HOME}/Downloads)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
