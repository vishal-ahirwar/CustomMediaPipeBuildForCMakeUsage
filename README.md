Building
Linux
Requirements
```
    Python 3: apt install python3
    Bazel 6.1.1 or according to the latest mediapipe build: https://github.com/bazelbuild/bazel/releases/
    Numpy: pip3 install numpy or create a virtual env and download the python stuff in it
```
Build and install OpenCV 4.7.0

```
wget -O opencv.zip https://github.com/opencv/opencv/archive/4.7.0.zip
wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/4.7.0.zip
unzip opencv.zip
unzip opencv_contrib.zip
mkdir -p opencv_build && cd opencv_build
cmake -DOPENCV_EXTRA_MODULES_PATH=../opencv_contrib-4.7.0/modules ../opencv-4.7.0
cmake --build .
cmake --install .
```
Run the build script
```
cd <path to libmediapipe>
./build-x86_64-linux.sh --config release --opencv_dir /usr/local
```

Running the Example
Linux & MacOS
Requirements

    CMake
```
cd <path to libmediapipe>/example
mkdir build && cd build
cmake -DMediaPipe_DIR=<libmediapipe build dir> -DCMAKE_BUILD_TYPE=Release ..
cmake --build .
chmod +x ./example
./example <libmediapipe data dir>
```
