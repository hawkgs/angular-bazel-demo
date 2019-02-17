workspace(name = 'angular_bazel_test_app')

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_typescript",
    url = "https://github.com/bazelbuild/rules_typescript/archive/0.22.1.zip",
    strip_prefix = "rules_typescript-0.22.1",
)

http_archive(
    name = "build_bazel_rules_nodejs",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/0.18.6/rules_nodejs-0.18.6.tar.gz"],
    sha256 = "1416d03823fed624b49a0abbd9979f7c63bbedfd37890ddecedd2fe25cccebc6",
)

http_archive(
    name = "angular",
    sha256 = "56f7b74390a78c87e49bf235983e18bdff21da7071870941d5801745a0a8b30f",
    strip_prefix = "angular-7.2.5",
    url = "https://github.com/angular/angular/archive/7.2.5.zip",
)

load("@build_bazel_rules_typescript//:package.bzl", "rules_typescript_dependencies")
rules_typescript_dependencies()

load("@build_bazel_rules_typescript//:defs.bzl", "ts_setup_workspace")
ts_setup_workspace()

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories", "npm_install")
node_repositories()

npm_install(
  name = "npm",
  package_json = "//:package.json",
  package_lock_json = "//:package-lock.json"
)
