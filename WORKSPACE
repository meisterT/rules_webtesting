# Copyright 2016 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################
#
workspace(name = "io_bazel_rules_webtesting")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "bazel_skylib",
    sha256 = "2b9af2de004d67725c9985540811835389b229c27874f2e15f5e319622a53a3b",
    strip_prefix = "bazel-skylib-e9fc4750d427196754bebb0e2e1e38d68893490a",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/archive/e9fc4750d427196754bebb0e2e1e38d68893490a.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/archive/e9fc4750d427196754bebb0e2e1e38d68893490a.tar.gz",
    ],
)

# NOTE: URLs are mirrored by an asynchronous review process. They must
#       be greppable for that to happen. It's OK to submit broken mirror
#       URLs, so long as they're correctly formatted. Bazel's downloader
#       has fast failover.

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "5f3b0304cdf0c505ec9e5b3c4fc4a87b5ca21b13d8ecc780c97df3d1809b9ce6",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/0.15.1/rules_go-0.15.1.tar.gz",
        "https://github.com/bazelbuild/rules_go/releases/download/0.15.1/rules_go-0.15.1.tar.gz",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "c0a5739d12c6d05b6c1ad56f2200cb0b57c5a70e03ebd2f7b87ce88cabf09c7b",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/0.14.0/bazel-gazelle-0.14.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/0.14.0/bazel-gazelle-0.14.0.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

load("//web:repositories.bzl", "browser_repositories", "web_test_repositories")

web_test_repositories()

browser_repositories(
    chromium = True,
    firefox = True,
    sauce = True,
)

http_archive(
    name = "io_bazel_rules_scala",
    sha256 = "6c69597f373a01989b9f7119bd5d28cffc9cc35d44d1f6440c409d8ef420057d",
    strip_prefix = "rules_scala-da5ba6d97a1abdadef89d509b30a9dcfde7ffbe4",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_scala/archive/da5ba6d97a1abdadef89d509b30a9dcfde7ffbe4.tar.gz",
        "https://github.com/bazelbuild/rules_scala/archive/da5ba6d97a1abdadef89d509b30a9dcfde7ffbe4.tar.gz",
    ],
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")

scala_repositories()

load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")

scala_register_toolchains()
