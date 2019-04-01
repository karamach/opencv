#############################
# BUILD OpenCV using cmake
#############################
# download opencv_contrib to $neorepo/third_party
# cd $neorepo/third_party/opencv
# mkdir -p bld/install
# cd bld
# cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=./install -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules -DPYTHON_EXECUTABLE=/usr/local/bin/python3 -DBUILD_opencv_python2=Off -DBUILD_opencv_python3=On -DPYTHON3_NUMPY_INCLUDE_DIRS=/usr/local/lib/python3.7/site-packages/numpy/core/include/ ..
# make -j4
# make install
# 
#############
# Test opencv
#############
# cd $neorepo/third_party/opencv
# cp BUILD_cv2 bld/install/include/opencv4/BUILD
# bazel build -c opt third_party/test:opencv_test
# bazel-bin/third_party/test/opencv_test third_party/test/1.jpg
#
####################
# Test opencv python
####################
# export PYTHONPATH=$neorepo/../third_party/opencv-xx/build/lib/python3
# bazel build -c opt --python_top=//third_party/test:python-3.7.2 //third_party/test:opencv_py_test
# bazel-out/darwin-py3-opt/bin/third_party/test/opencv_py_test

licenses(["notice"])

cc_library(
    name = "opencv",
    srcs = glob(["bld/install/lib/**/*.dylib"]),
    deps = ["//third_party/opencv/bld/install/include/opencv4:opencv2"],
    includes = ["bld/install/include/opencv4"],    
    linkstatic = 1,
    visibility = ["//visibility:public"],
)

py_library(
    name = "opencv_py",
    imports = ["bld/lib/python3"],
    visibility = ["//visibility:public"],
)

