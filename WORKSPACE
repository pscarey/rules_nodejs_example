workspace(name = "rules_nodejs_example")

git_repository(
    name = "bazel_skylib",
    remote = "https://github.com/bazelbuild/bazel-skylib.git",
    tag = "0.5.0",
)

git_repository(
    name = "build_bazel_rules_nodejs",
    remote = "https://github.com/bazelbuild/rules_nodejs.git",
    tag = "0.15.1",
)

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories", "yarn_install")

node_repositories(
  node_version = "8.12.0",
  node_repositories = {
      "8.12.0-darwin_amd64": ("node-v8.12.0-darwin-x64.tar.gz", "node-v8.12.0-darwin-x64", "ca131b84dfcf2b6f653a6521d31f7a108ad7d83f4d7e781945b2eca8172064aa"),
      "8.12.0-linux_amd64": ("node-v8.12.0-linux-x64.tar.gz", "node-v8.12.0-linux-x64", "3df19b748ee2b6dfe3a03448ebc6186a3a86aeab557018d77a0f7f3314594ef6"),
      "8.12.0-windows_amd64": ("node-v8.12.0-win-x64.zip", "node-v8.12.0-win-x64", "9b22c9b23148b61ea0052826b3ac0255b8a3a542c125272b8f014f15bf11b091"),
  },
  node_urls = [
      "https://nodejs.org/dist/v{version}/{filename}",
  ],
  yarn_version = "1.10.1",
  yarn_repositories = {
     "1.10.1": ("yarn-v1.10.1.tar.gz", "yarn-v1.10.1", "97bf147cb28229e66e4e3c5733a93c851bbcb0f10fbc72696ed011774f4c6f1b"),
  },
  yarn_urls = ["https://github.com/yarnpkg/yarn/releases/download/v{version}/{filename}"],
  package_json = ["//:package.json"],
)

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)