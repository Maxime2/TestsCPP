Various tests (in C++) language.

1. TestMath -- How long does it take to compute a log, a pow, an exponent, etc?
   Is division slower than multiplication?
   There are 3 makefiles in TestMath. Two should to be used with GNU C++ (they only differ in the optimization flag), another with the Intel C++ compiler.

    To build with g++ on x86 platform type:

    make -f Makefile.gcc_x86

    To build with g++ on platform other than x86 type:

    make -f Makefile.gcc_other
    
    There is also a makefile for the Intel compiler. To better understand benchmark results,
    please, read my blog entry. This should be important: 
    http://searchivarius.org/blog/problem-previous-version-intels-library-benchmark

    To build with the Intel compiler type:

    make -f Makefile.icc
              
2.  BenchCPUCores -- a stupid code to get the number of cores empirically.  Compile the code (type make) and execute ./bench.sh with a large parameter N. This script runs the compiled binary using different number of threads, each of which carries out the same task. While the number of threads does not exceed the number of actual cores, the run-time remains constant. When, you see the increase in the run-time, the number of threads exceeds the number of actual cores. The parameter N should be chosen large enough. For instance:

    ./bench.sh 1024 
