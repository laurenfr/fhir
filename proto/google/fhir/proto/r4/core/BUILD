load("//bazel:proto.bzl", "fhir_proto_library")
load("//bazel:protogen.bzl", "gen_fhir_protos")

package(
    default_visibility = ["//visibility:public"],
)

licenses(["notice"])

fhir_proto_library(
    srcs = ["datatypes.proto"],
    proto_deps = [
        ":codes_proto",
        ":valuesets_proto",
        "//proto/google/fhir/proto:annotations_proto",
    ],
    proto_library_prefix = "datatypes",
)

gen_fhir_protos(
    name = "core",
    package = "//spec:fhir_r4",
)


fhir_proto_library(
    srcs = ["codes.proto"],
    proto_deps = [
        "//proto/google/fhir/proto:annotations_proto",
    ],
    proto_library_prefix = "codes",
)

fhir_proto_library(
    srcs = ["valuesets.proto"],
    proto_deps = [
        "//proto/google/fhir/proto:annotations_proto",
    ],
    proto_library_prefix = "valuesets",
)

fhir_proto_library(
    srcs = [
        "extensions.proto",
    ],
    proto_deps = [
        ":codes_proto",
        ":datatypes_proto",
        ":valuesets_proto",
        "//proto/google/fhir/proto:annotations_proto",
    ],
    proto_library_prefix = "extensions",
)

# We also make the .proto files readable for testing.
filegroup(
    name = "testdata",
    srcs = glob([
        "*.proto",
    ]),
)
