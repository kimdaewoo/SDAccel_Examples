COMMON_REPO := ../../../

include $(COMMON_REPO)/utility/boards.mk
include $(COMMON_REPO)/libs/xcl/xcl.mk
include $(COMMON_REPO)/libs/opencl/opencl.mk

# Host Application
host_SRCS=./src/host.cpp $(xcl_SRCS)
host_HDRS=$(xcl_HDRS)
host_CXXFLAGS=-I./src/ $(xcl_CXXFLAGS) $(opencl_CXXFLAGS)
host_LDFLAGS=$(opencl_LDFLAGS)

# Kernel
adder_SRCS=./src/adder.cpp
adder_CLFLAGS= -k adder
adder_DEVICES=xilinx:adm-pcie-7v3:1ddr:3.2 xilinx:adm-pcie-ku3:2ddr-xpr:3.2

EXES=host
XCLBINS=adder

# check
check_EXE=host
check_XCLBINS=adder
check_DEVICES=xilinx:adm-pcie-7v3:1ddr:3.2 xilinx:adm-pcie-ku3:2ddr-xpr:3.2

CHECKS=check

include $(COMMON_REPO)/utility/rules.mk

