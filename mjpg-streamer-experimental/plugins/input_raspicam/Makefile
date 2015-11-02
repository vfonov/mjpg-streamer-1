###############################################################
#
# Purpose: Makefile for "M-JPEG Streamer"
# Author.: Tom Stoeveken (TST)
# Version: 0.3
# License: GPL
#
###############################################################

CC = gcc

OTHER_HEADERS = ../../mjpg_streamer.h ../../utils.h ../output.h ../input.h

CFLAGS += -O1  -DLINUX -D_GNU_SOURCE -Wall -shared -fPIC  

# MMAL headers
CFLAGS += -I/opt/vc/include
CFLAGS += -I/opt/vc/include/interface/
CFLAGS += -I/opt/vc/include/interface/vcos
CFLAGS += -I/opt/vc/include/interface/vcos/pthreads
CFLAGS += -I/opt/vc/include/interface/vmcs_host
CFLAGS += -I/opt/vc/include/interface/vmcs_host/linux

# MMAL libraries
LFLAGS += -L/opt/vc/lib -lmmal_core -lmmal_util -lmmal_vc_client -lvcos -lbcm_host

all: input_raspicam.so

clean:
	rm -f *.a *.o core *~ *.so *.lo

input_raspicam.so: $(OTHER_HEADERS) input_raspicam.c
	$(CC) $(CFLAGS) -o $@ input_raspicam.c $(LFLAGS)
