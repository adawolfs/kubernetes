package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "args.go",
        "gvpackages.go",
        "gvtype.go",
    ],
    deps = [
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/k8s.io/code-generator/cmd/client-gen/types:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)

go_test(
    name = "go_default_test",
    srcs = ["gvpackages_test.go"],
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/spf13/pflag:go_default_library",
        "//vendor/k8s.io/code-generator/cmd/client-gen/types:go_default_library",
    ],
)
