load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/flarebuild/ristretto

gazelle(name = "gazelle")

go_library(
    name = "go_default_library",
    srcs = [
        "cache.go",
        "policy.go",
        "ring.go",
        "sketch.go",
        "store.go",
        "ttl.go",
    ],
    importpath = "github.com/flarebuild/ristretto",
    visibility = ["//visibility:public"],
    deps = ["//z:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "cache_test.go",
        "policy_test.go",
        "ring_test.go",
        "sketch_test.go",
        "store_test.go",
        "stress_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//sim:go_default_library",
        "//z:go_default_library",
        "@com_github_stretchr_testify//require:go_default_library",
    ],
)
