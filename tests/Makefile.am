#the name that the program will called once compiled
check_PROGRAMS	=	runner

AM_CPPFLAGS	=	-HAVE_CGI $(OPENCV_CFLAGS)

#the source files used to build the runner target
runner_SOURCES	=	runner.cpp \
				CvTileTestSuite.cpp \
				TilerTestSuite.cpp

#libraries that will be linked
runner_LDADD	=	-lcgi_core $(OPENCV_LIBS) $(top_builddir)/src/libcvtile.la

#
# Nothing below this line should need customization on a per-project basis.
#

all: check

# A rule that runs the unit tests
check: $(check_PROGRAMS)
	rm -f tdata*
	@for PROGRAM in $(check_PROGRAMS:%=./%); do echo $$PROGRAM; $$PROGRAM; done

# compile all of the generated source code files
.cpp.o:
	g++ -g -Wall -I/usr/local/cxxtest/include/ -I../src/ -c -o $@ $<

# How to generate the test runner (this is the scaffolding that makes things go)
runner.cpp: 
	cxxtestgen.pl --error-printer --root -o $@

# turn your test files (the headers) into source code
.hpp.cpp:
	cxxtestgen.pl --part -o $@ $<

clean:
	rm -f $(runner_SOURCES) $(runner_SOURCES:.cpp=.o) $(check_PROGRAMS) $(check_PROGRAMS:${EXEEXT}=) tdata*

distclean: clean

.NOTPARALLEL:
