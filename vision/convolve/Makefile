# Convolve Application

include ../../utility/boards.mk
include ../../libs/xcl/xcl.mk
include ../../libs/opencv/opencv.mk
include ../../libs/opencl/opencl.mk

# convolve Host Application
convolve_SRCS=src/convolve.cpp $(xcl_SRCS)
convolve_HDRS= $(xcl_HDRS)
convolve_CXXFLAGS=$(xcl_CXXFLAGS) $(opencl_CXXFLAGS) $(opencv_CXXFLAGS)
convolve_LDFLAGS=$(opencl_LDFLAGS) $(opencv_LDFLAGS)

# convolve Kernel
krnl_convolve_SRCS=src/krnl_convolve.cl
krnl_convolve_CLFLAGS=--nk krnl_convolve:3

EXES=convolve
XCLBINS=krnl_convolve

# check
check_EXE=convolve
check_XCLBINS=krnl_convolve
check_ARGS=data/input_buffer_raw.txt data/filter_buffer_raw.txt data/output_buffer_raw.txt

CHECKS=check

include ../../utility/rules.mk

