# Bazel workspace created by @bazel/create 5.3.1

# Declares that this directory is the root of a Bazel workspace.
# See https://docs.bazel.build/versions/main/build-ref.html#workspace
workspace(
    # How this workspace would be referenced with absolute labels from another workspace
    name = "bazel_emscripten_test",
)

load("//tools:bazel_deps.bzl", "fetch_dependencies")

fetch_dependencies()

load("@build_bazel_rules_nodejs//:repositories.bzl", "build_bazel_rules_nodejs_dependencies")

build_bazel_rules_nodejs_dependencies()

# The npm_install rule runs yarn anytime the package.json or package-lock.json file changes.
# It also extracts any Bazel rules distributed in an npm package.
load("@build_bazel_rules_nodejs//:index.bzl", "npm_install")

npm_install(
    # Name this npm so that Bazel Label references look like @npm//package
    name = "npm",
    package_json = "//:package.json",
    package_lock_json = "//:package-lock.json",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "emsdk",
    sha256 = "98e2a5b5aefd6beb8265991cdde2992f4eac1aacbad52da425f877b823de9560",
    strip_prefix = "emsdk-3.1.8/bazel",
    url = "https://github.com/emscripten-core/emsdk/archive/refs/tags/3.1.8.tar.gz",
)

load("@emsdk//:deps.bzl", emsdk_deps = "deps")
emsdk_deps()

load("@emsdk//:emscripten_deps.bzl", emsdk_emscripten_deps = "emscripten_deps")
emsdk_emscripten_deps(emscripten_version = "3.1.8")
