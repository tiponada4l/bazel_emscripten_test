Demonstrates https://github.com/emscripten-core/emsdk/issues/1020

```
$ bazel build ...
INFO: Invocation ID: a4d1f6ef-70b5-4fda-8103-b7a514feec57
DEBUG: /private/var/tmp/_bazel_johnfirebaugh/29f2aec223a33f0d4bb2f83ccca4211f/external/build_bazel_rules_nodejs/index.bzl:65:14: node_repository attribute not set and no repository named 'nodejs_toolchains' exists; installing default node
ERROR: /private/var/tmp/_bazel_johnfirebaugh/29f2aec223a33f0d4bb2f83ccca4211f/external/emsdk/emscripten_toolchain/BUILD.bazel:26:10: no such package '@nodejs//': The repository '@nodejs' could not be resolved: Repository '@nodejs' is not defined and referenced by '@emsdk//emscripten_toolchain:link-emscripten'
ERROR: Analysis of target '//:hello-world-wasm' failed; build aborted:
INFO: Elapsed time: 0.191s
INFO: 0 processes.
FAILED: Build did NOT complete successfully (22 packages loaded, 249 targets configured)
    Fetching @local_config_xcode; Fetching the default Xcode version
    Fetching @emscripten_bin_mac; Restarting.
```
