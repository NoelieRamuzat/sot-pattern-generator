#
#  Copyright
#

ADD_DEFINITIONS(-DDEBUG=2)

ADD_UNIT_TEST(main_test main.cc)

TARGET_LINK_LIBRARIES(main_test
  pg
  )

SET(urdfpath ${TALOS_DATA_PREFIX}/share/talos_data/urdf/talos_reduced_wpg.urdf)
SET(srdfpath ${TALOS_DATA_PREFIX}/share/talos_data/srdf/talos_wpg.srdf)

TARGET_COMPILE_DEFINITIONS(main_test PUBLIC
  URDF_FULL_PATH="${urdfpath}" SRDF_FULL_PATH="${srdfpath}")
