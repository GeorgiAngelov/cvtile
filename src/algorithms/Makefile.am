LINK = $(LIBTOOL) --mode=link $(CC) -o  $@ $(CUDA_LDFLAGS) -use-fast-math $(CUDA_LIBS) $(OPENCV_LIBS)

EXAMPLE_LIBRARY_VERSION=0:0:0

noinst_LTLIBRARIES = libcvtile_algorithms.la

AM_CPPFLAGS = -I..

libcvtile_algorithms_la_LDFLAGS = -version-info $(EXAMPLE_LIBRARY_VERSION) @LTLIBOBJS@ 
libcvtile_algorithms_la_SOURCES = 
libcvtile_algorithms_la_LIBADD = 
				