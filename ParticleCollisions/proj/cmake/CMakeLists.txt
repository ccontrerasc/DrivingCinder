cmake_minimum_required( VERSION 3.10 FATAL_ERROR )
set( CMAKE_VERBOSE_MAKEFILE ON )

project( ParticleCollisions )

get_filename_component( CINDER_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../../.." ABSOLUTE )
get_filename_component( APP_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../" ABSOLUTE )

include( "${CINDER_PATH}/proj/cmake/modules/cinderMakeApp.cmake" )

set ( SRC_FILES
		${APP_PATH}/src/ParticleCollisions.cpp
)

ci_make_app(
	SOURCES     ${SRC_FILES}
	INCLUDES    ${APP_PATH}/include
		    ${APP_PATH}/include/PerlinNoiseClasses
	CINDER_PATH ${CINDER_PATH}
)
