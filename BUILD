package(default_visibility = ["//visibility:public"])

load("@angular//:index.bzl", "ng_module")

ng_module(
  name = "main",
  srcs = ["main.ts"],
  tsconfig = "//:tsconfig.json",
  deps = ["//app"]
)

load("@build_bazel_rules_nodejs//:defs.bzl", "rollup_bundle")

rollup_bundle(
  name = "bundle",
  entry_point = "main.js",
  deps = [":main"],
)
