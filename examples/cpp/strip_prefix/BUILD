load("//bazel:cc_grpc_library.bzl", "cc_grpc_library")

proto_library(
    name = "messages_proto",
    srcs = ["messages.proto"],
    import_prefix = "custom/prefix",
    strip_import_prefix = "",
)

proto_library(
    name = "service_proto",
    srcs = ["service.proto"],
    deps = [":messages_proto"]
)

cc_proto_library(
    name = "messages_cc_proto",
    deps = [":messages_proto"],
)

cc_proto_library(
    name = "service_cc_proto",
    deps = [":service_proto"],
)

cc_grpc_library(
    name = "service_cc_grpc",
    srcs = [":service_proto"],
    grpc_only = True,
    deps = [":service_cc_proto"],
)
