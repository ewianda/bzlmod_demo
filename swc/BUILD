load("@aspect_rules_swc//swc:swc.bzl", "swc")
load("@bazel_skylib//rules:diff_test.bzl", "diff_test")

# Runs `swc in.ts > ../../bazel-bin/examples/simple/in.js`
# You can run `bazel build --subcommands //examples/simple:transpile`
# to see the exact command line Bazel runs.
# Note that by default, sources are found by glob(["**/*.ts"])
swc(name = "transpile")

# Assert that the output of "transpile" rule matches the expected file.
diff_test(
    name = "test",
    # This is a pre-declared output of the "transpile" rule, so we can refer to it directly using a Bazel label
    # even though the file itself is generated by Bazel in ../../bazel-bin/examples/simple/in.js
    file1 = "in.js",
    # The expected result contents
    file2 = "expected.js",
)
