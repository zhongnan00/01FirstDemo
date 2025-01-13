# Navigaiton 

## opencv 
```shell

git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
cd opencv
git checkout 4.x  # Replace '4.x' with the desired version
cd ../opencv_contrib
git checkout 4.x

## refer command;
# $ cd <opencv_build_directory>
# $ cmake -DOPENCV_EXTRA_MODULES_PATH=<opencv_contrib>/modules <opencv_source_directory>
# $ make -j5

cd ../opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=Release \
      -D CMAKE_INSTALL_PREFIX=/usr/local \
      -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
      -D WITH_TBB=ON \
      -D WITH_V4L=ON \
      -D WITH_OPENGL=ON \
      -D BUILD_EXAMPLES=ON ..
make -j$(nproc)
sudo make install
sudo ldconfig




pkg-config --cflags --libs opencv4
ls /usr/local/include/opencv4/opencv2/aruco.hpp

```
