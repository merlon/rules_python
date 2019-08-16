# Copyright 2017 The Bazel Authors. All rights reserved.
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

workspace(name = "rules_python")

###################################
# Test data for WHL tool testing. #
###################################

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_file")

http_file(
    name = "apispec_2_0_1_whl",
    downloaded_file_path = "apispec-2.0.1-py2.py3-none-any.whl",
    sha256 = "427293594699c77753b8fdc6d78d8dfe267c394df5186c236d57f6ef1af95027",
    # From https://pypi.python.org/pypi/apispec
    urls = [("https://pypi.python.org/packages/ea/c3/" +
             "1f60ae577a1f92a60bd254d3d8b7747f8ba02e5d5638bde79ea17ae45208/" +
             "apispec-2.0.1-py2.py3-none-any.whl")],
)

http_file(
    name = "gunicorn_19_9_0_whl",
    downloaded_file_path = "gunicorn-19.9.0-py2.py3-none-any.whl",
    sha256 = "aa8e0b40b4157b36a5df5e599f45c9c76d6af43845ba3b3b0efe2c70473c2471",
    # From https://pypi.python.org/pypi/gunicorn
    urls = [("https://pypi.python.org/packages/8c/da/" +
             "b8dd8deb741bff556db53902d4706774c8e1e67265f69528c14c003644e6/" +
             "gunicorn-19.9.0-py2.py3-none-any.whl")],
)

http_file(
    name = "pyOpenSSL_19_0_0_whl",
    downloaded_file_path = "pyOpenSSL-19.0.0-py2.py3-none-any.whl",
    sha256 = "c727930ad54b10fc157015014b666f2d8b41f70c0d03e83ab67624fd3dd5d1e6",
    # From https://pypi.python.org/pypi/pyOpenSSL
    urls = [("https://pypi.python.org/packages/01/c8/" +
             "ceb170d81bd3941cbeb9940fc6cc2ef2ca4288d0ca8929ea4db5905d904d/" +
             "pyOpenSSL-19.0.0-py2.py3-none-any.whl")],
)

http_file(
    name = "google_cloud_spanner_1_9_0_whl",
    downloaded_file_path = "google_cloud_spanner-1.9.0-py2.py3-none-any.whl",
    sha256 = "963d0afe48bef9f8c7fef3982aa69ea46c12703c1379f66f52f5d7ced47a0b42",
    # From https://pypi.python.org/pypi/google-cloud-spanner
    urls = [("https://pypi.python.org/packages/b1/df/" +
             "96686bc6abafacb579334f8c61be2f025f1be161d266893d17b47afd7685/" +
             "google_cloud_spanner-1.9.0-py2.py3-none-any.whl")]
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "bazel_federation",
    url = "https://github.com/bazelbuild/bazel-federation/archive/4da9b5f83ffae17613fa025a0701fa9db9350d41.zip",
    sha256 = "5b1cf980e327a8f30fc81c00c04007c543e17c09ed612fb645753936de790ed7",
    strip_prefix = "bazel-federation-4da9b5f83ffae17613fa025a0701fa9db9350d41",
    type = "zip",
)

load("@bazel_federation//:repositories.bzl", "rules_python_deps")
rules_python_deps()

load("@bazel_federation//setup:rules_python.bzl",  "rules_python_setup")
rules_python_setup(use_pip=True)

load("//:internal_deps.bzl", "rules_python_internal_deps")
rules_python_internal_deps()

load("//:internal_setup.bzl", "rules_python_internal_setup")
rules_python_internal_setup()
