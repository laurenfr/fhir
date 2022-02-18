workspace(name = "com_google_fhir")

load("//bazel:dependencies.bzl", "fhirproto_dependencies")
fhirproto_dependencies(core_lib = True)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
protobuf_deps()

load("//bazel:workspace.bzl", "fhirproto_workspace")
fhirproto_workspace(core_lib = True)

load("@rules_python//python:pip.bzl", "pip_install")
pip_install(
   name = "fhir_bazel_pip_dependencies",
   requirements = "//bazel:requirements.txt",
)

load("//bazel:go_dependencies.bzl", "fhir_go_dependencies")
fhir_go_dependencies()

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "google_bazel_common",
    sha256 = "18f266d921db1daa2ee9837343938e37fa21e0a8b6a0e43a67eda4c30f62b812",
    strip_prefix = "bazel-common-eb5c7e5d6d2c724fe410792c8be9f59130437e4a",
    urls = ["https://github.com/google/bazel-common/archive/eb5c7e5d6d2c724fe410792c8be9f59130437e4a.zip"],
)

# Needed for the jarjar_library rule.
load("@google_bazel_common//:workspace_defs.bzl", "google_common_workspace_rules")
google_common_workspace_rules()

http_archive(
    name = "com_github_grpc_grpc",
    sha256 = "b391a327429279f6f29b9ae7e5317cd80d5e9d49cc100e6d682221af73d984a6",
    strip_prefix = "grpc-93e8830070e9afcbaa992c75817009ee3f4b63a0",  # v1.24.3 with fixes
    urls = ["https://github.com/grpc/grpc/archive/93e8830070e9afcbaa992c75817009ee3f4b63a0.zip"],
)

