clang++-6.0 -o main index.cpp -fsanitize=address -g -fno-omit-frame-pointer -fno-optimize-sibling-calls
dpkg -L llvm-6.0 | grep symbolize
/usr/lib/llvm-6.0/bin/llvm-symbolizer
\\
clang++-6.0 -std=c++17 -o main index.cpp -fsanitize=address -g 
-fno-omit-frame-pointer -fno-optimize-sibling-calls
\\
ASAN_SYMBOLIZER_PATH=/usr/lib/llvm-6.0/bin/llvm-symbolizer ./main
\\
