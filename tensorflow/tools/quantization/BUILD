# Description:
#   Utilities for quantizing TensorFlow graphs to lower bit depths.

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

py_library(
    name = "quantize_graph_lib",
    srcs = ["quantize_graph.py"],
    srcs_version = "PY2AND3",
    deps = ["//tensorflow:tensorflow_py"],
)

py_binary(
    name = "quantize_graph",
    srcs = ["quantize_graph.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:platform",
        "@six_archive//:six",
    ],
)

py_test(
    name = "quantize_graph_test",
    size = "small",
    srcs = [
        "quantize_graph_test.py",
    ],
    srcs_version = "PY2AND3",
    tags = ["nomsan"],  # http://b/32242946
    deps = [
        ":quantize_graph",
        "//tensorflow/python:framework",
    ],
)

py_binary(
    name = "graph_to_dot",
    srcs = [
        "graph_to_dot.py",
    ],
    main = "graph_to_dot.py",
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:platform",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
