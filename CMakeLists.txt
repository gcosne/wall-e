cmake_minimum_required(VERSION 2.8)

# Basic CMAKE file for opencv program
# cp to /src 

# project name
PROJECT( wall-e-calib )

# change only if more packages are needed
FIND_PACKAGE( OpenCV REQUIRED )

# arg_0 is the excutable name
# arg_x are the .cpp files
ADD_EXECUTABLE( build/intrinsic src/find_intrinsic.cpp )
ADD_EXECUTABLE( build/stereo src/calibrate_stereo.cpp )
ADD_EXECUTABLE( build/disparity src/stereo_disparity.cpp )

# link needed libraries, should not have to change
TARGET_LINK_LIBRARIES( build/intrinsic ${OpenCV_LIBS} )
TARGET_LINK_LIBRARIES( build/stereo ${OpenCV_LIBS} )
TARGET_LINK_LIBRARIES( build/disparity ${OpenCV_LIBS} )
