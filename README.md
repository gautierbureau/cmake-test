``` bash
cmake -S . -B build
cmake --build build 
cmake --install build

cmake -S . -B build --graphviz=toto

cmake --build build --target install

cmake -S . -B build -DCMAKE_INSTALL_PREFIX=

cmake --build build --target install --config Release
cmake --build build --target install --config Release --clean-first

cmake -S . -B build -DCMAKE_INSTALL_PREFIX= -DCMAKE_BUILD_TYPE=Release
cmake --build build --target install --config Release
```