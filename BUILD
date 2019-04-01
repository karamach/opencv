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

