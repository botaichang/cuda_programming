############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2012-02-07          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan </author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com</email>
############################################################################

# collect source files
cmake_minimum_required(VERSION 2.8)
find_package(CUDA QUIET REQUIRED)
find_package(OpenCV REQUIRED)

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW1_files main.cpp reference_calc.cpp compare.cpp)

cuda_add_executable(HW1 ${HW1_files} ${hdr} ${cu})
target_link_libraries( HW1 ${OpenCV_LIBS} )
