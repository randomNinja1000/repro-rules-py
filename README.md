# Instructions

```
(cd repo1 && bazel run //python/test:test)
```
passes.

```
(cd repo2 && bazel run //python/test:test)
```
passes.

Comment / uncomment the load in repo1/python/BUILD.bazel

```
(cd repo2 && bazel run //python/test:test)
```
now fails and the `sys.path` does not contain `repo1` anymore.

Unfortunately, it seems with rules_py imports do not "properly cross repos".
