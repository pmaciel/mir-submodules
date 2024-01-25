cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

find_package(ecbuild 3.8 REQUIRED)

project(MirSubmodules VERSION 0.0.0.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)

ecbuild_bundle_initialize()

set(ENABLE_MIR_TESTS_REGRESS ON CACHE BOOL "" FORCE)

ecbuild_bundle(PROJECT ecbuild GIT "ssh://git@github.com:ecmwf/ecbuild.git" BRANCH master  MANUAL)
ecbuild_bundle(PROJECT eccodes GIT "ssh://git@github.com:ecmwf/eccodes.git" BRANCH develop MANUAL)
ecbuild_bundle(PROJECT eckit   GIT "ssh://git@github.com:ecmwf/eckit.git"   BRANCH develop MANUAL)
ecbuild_bundle(PROJECT atlas   GIT "ssh://git@github.com:ecmwf/atlas.git"   BRANCH develop MANUAL)
ecbuild_bundle(PROJECT mir     GIT "ssh://git@github.com:ecmwf/mir.git"     BRANCH develop MANUAL)

ecbuild_bundle_finalize()

