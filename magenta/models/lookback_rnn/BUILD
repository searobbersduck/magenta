# Copyright 2016 Google Inc. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Description:
# Lookback RNN model.

licenses(["notice"])  # Apache 2.0

py_binary(
    name = "lookback_rnn_create_dataset",
    srcs = ["lookback_rnn_create_dataset.py"],
    srcs_version = "PY2AND3",
    visibility = [
        # internal pipeline runner
    ],
    deps = [
        ":lookback_rnn_encoder_decoder",
        "//magenta/models/shared:melody_rnn_create_dataset",
        # tensorflow dep
    ],
)

py_library(
    name = "lookback_rnn_encoder_decoder",
    srcs = ["lookback_rnn_encoder_decoder.py"],
    srcs_version = "PY2AND3",
    visibility = [
        # internal dev models
    ],
    deps = [
        "//magenta/lib:melodies_lib",
    ],
)

py_library(
    name = "lookback_rnn_generator",
    srcs = ["lookback_rnn_generator.py"],
    srcs_version = "PY2AND3",
    visibility = ["//magenta/interfaces:generator_interfaces"],
    deps = [
        ":lookback_rnn_encoder_decoder",
        ":lookback_rnn_graph",
        "//magenta/models/shared:melody_rnn_sequence_generator",
        "//magenta/protobuf:generator_py_pb2",
    ],
)

py_binary(
    name = "lookback_rnn_generate",
    srcs = ["lookback_rnn_generate.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":lookback_rnn_generator",
        "//magenta/models/shared:melody_rnn_generate",
        # tensorflow dep
    ],
)

py_library(
    name = "lookback_rnn_graph",
    srcs = ["lookback_rnn_graph.py"],
    srcs_version = "PY2AND3",
    visibility = [
        # internal dev models
    ],
    deps = [
        "//magenta/lib:tf_lib",
        "//magenta/models/shared:melody_rnn_graph",
    ],
)

py_binary(
    name = "lookback_rnn_train",
    srcs = ["lookback_rnn_train.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":lookback_rnn_encoder_decoder",
        ":lookback_rnn_graph",
        "//magenta/models/shared:melody_rnn_train",
        # tensorflow dep
    ],
)
