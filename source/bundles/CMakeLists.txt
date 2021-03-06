INCLUDE_DIRECTORIES(
  ${CMAKE_SOURCE_DIR}/
  ${CMAKE_SOURCE_DIR}/core/
  ${CMAKE_SOURCE_DIR}/bundles/

  ${izenelib_INCLUDE_DIRS}
  ${izenecma_INCLUDE_DIRS}
  ${izenejma_INCLUDE_DIRS}
  ${ilplib_INCLUDE_DIRS}
  ${idmlib_INCLUDE_DIRS}
  ${imllib_INCLUDE_DIRS}
  ${Boost_INCLUDE_DIRS}
  ${TokyoCabinet_INCLUDE_DIRS}
  ${Glog_INCLUDE_DIRS}
  )

FILE(GLOB_RECURSE index_SRC "index/*.cpp")
FILE(GLOB_RECURSE mining_SRC "mining/*.cpp")
ADD_DEFINITIONS("-fno-strict-aliasing")
ADD_LIBRARY(sf1r_bundle_index ${index_SRC})
ADD_LIBRARY(sf1r_bundle_mining ${mining_SRC})

INSTALL(TARGETS
    sf1r_bundle_index
    sf1r_bundle_mining
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    COMPONENT sf1r_libraries)
