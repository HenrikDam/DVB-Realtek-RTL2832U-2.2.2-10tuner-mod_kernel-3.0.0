# Copyright (C) 2011 Xgaz <xgazza@inwind.it>
# License: GPL
# RTL2832U Driver


# Change BASEDIR accordingly to your paths (ambrosa)
#BASEDIR := /home/ambrosa/GIT
#SOURCEDIR := $(BASEDIR)/DVB-Realtek-RTL2832U-2.2.2-10tuner-mod_kernel-3.0.0/RTL2832-2.2.2_kernel-3.0.0

SOURCEDIR := $(PWD)
# ----------------------------------------

dvb-usb-rtl2832u-objs := demod_rtl2832.o dvbt_demod_base.o dvbt_nim_base.o \
	foundation.o math_mpi.o nim_rtl2832_mxl5007t.o nim_rtl2832_fc2580.o \
	nim_rtl2832_mt2266.o rtl2832u.o rtl2832u_fe.o rtl2832u_io.o \
	tuner_mxl5007t.o tuner_fc2580.o tuner_mt2266.o tuner_tua9001.o \
	nim_rtl2832_tua9001.o tuner_fc0012.o nim_rtl2832_fc0012.o demod_rtl2836.o \
	dtmb_demod_base.o dtmb_nim_base.o nim_rtl2836_fc2580.o 	nim_rtl2836_mxl5007t.o \
	tuner_e4000.o nim_rtl2832_e4000.o tuner_mt2063.o demod_rtl2840.o \
	tuner_max3543.o nim_rtl2832_mt2063.o nim_rtl2832_max3543.o \
	nim_rtl2840_mt2063.o nim_rtl2840_max3543.o qam_demod_base.o qam_nim_base.o \
	tuner_tda18272.o nim_rtl2832_tda18272.o rtl2832u_ioctl.o nim_rtl2832_fc0013.o \
	tuner_fc0013.o

obj-m += dvb-usb-rtl2832u.o

EXTRA_CFLAGS += -I$(SOURCEDIR)/include/ \
		-I$(KBUILD_SRC)/drivers/media/dvb/dvb-usb/ \
		-I$(KBUILD_SRC)/drivers/media/dvb/dvb-core/ \
		-I$(KBUILD_SRC)/drivers/media/dvb/frontends/ \
		-I$(KBUILD_SRC)/drivers/media/common/tuners/

KINS = /lib/modules
KDIR = /usr/src/linux-headers-`uname -r`

default:
	make -C $(KDIR) SUBDIRS=$(PWD) modules

install:
	cp dvb-usb-rtl2832u.ko $(KINS)/`uname -r`/kernel/drivers/media/dvb/dvb-usb/ 
	depmod -a

clean:
	-rm -f  *.o  *.ko *.mod.c .*.o.cmd  .*.o.d  .*.ko.cmd Module.symvers Module.markers modules.order
	-rm -rf .tmp_versions