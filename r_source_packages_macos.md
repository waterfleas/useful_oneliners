**Step-by-step Instructions to install R packages from source on macos in 2020**\n
(most recent test on macos10.15.5 and R3.6.2)\n\n
There is a known issue with openmp and clang when installing from source on macos - heres the fix.\n\n



1. brew install llvm

2.  cat << EOF >> ~/.R/Makevars  
CC=/usr/local/Cellar/llvm/10.0.0_3/bin/clang  
CXX=/usr/local/Cellar/llvm/10.0.0_3/bin/clang++  
CXX1X=/usr/local/Cellar/llvm/10.0.0_3/bin/clang++  
LDFLAGS=-L/usr/local/Cellar/llvm/10.0.0_3/lib -Wl,-rpath,/usr/local/Cellar/llvm/10.0.0_3/lib  
CXXFLAGS=-I/usr/local/Cellar/llvm/10.0.0_3/include  
FLIBS=-L/usr/local/Cellar/gcc/10.1.0/lib/gcc/10  
EOF  

__NOTE__: version numbers are lieky to change very quickly so this will need to be confirmed on next install
