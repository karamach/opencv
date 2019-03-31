cc_library(
    name = "opencv",
    srcs = glob(["build/install/lib/**/*.dylib"]),
    deps = ["//build/install/include/opencv4:opencv2"],
    includes = ["build/install/include/opencv4"],    
    linkstatic = 1,
    visibility = ["//visibility:public"],
)

py_library(
    name = "opencv_py",
    imports = ["build/lib/python3"],
    visibility = ["//visibility:public"],
)

