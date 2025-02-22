# std4

Work in progress standard library for Lean 4. This is a collection of data structures and tactics intended for use by both computer-science applications and mathematics applications of Lean 4.

# Build instructions

* Get the newest version of `elan`. If you already have installed a version of Lean, you can run
  ```
  elan self update
  ```
  If the above command fails, or if you need to install `elan`, run
  ```
  curl https://raw.githubusercontent.com/leanprover/elan/master/elan-init.sh -sSf | sh
  ```
  If this also fails, follow the instructions under `Regular install` [here](https://leanprover-community.github.io/get_started.html).
* To build `std4` run `lake build`. To build and run all tests, run `make`.
* If you added a new file, run the command `scripts/updateStd.sh` to update the
  imports.

# Documentation

You can generate `std4`'s documentation with

```text
# if you're generating documentation for the first time
> lake -Kdoc=on update
...
# actually generate the documentation
> lake -Kdoc=on build Std:docs
...
> ls build/doc/index.html
build/doc/index.html
```

The top-level HTML file will be located at `build/doc/Std.html`, though to actually expose the
documentation as a server you need to

```text
> cd build/doc
> python3 -m http.server
Serving HTTP on :: port 8000 (http://[::]:8000/) ...
```

Note that documentation for the latest nightly of `std4` is available as part of [the Mathlib 4
documentation][mathlib4 docs].

[mathlib4 docs]: https://leanprover-community.github.io/mathlib4_docs/Std.html

# Contributing

Every pull request should have exactly one of the status labels `awaiting-review`, `awaiting-author`
or `WIP` (in progress).
To change the status label of a pull request, add a comment containing one of these options and
_nothing else_.
This will remove the previous label and replace it by the requested status label.

One of the easiest ways to contribute is to find a missing proof and complete it. The
[`proof_wanted`](https://github.com/search?q=repo%3Aleanprover%2Fstd4+proof_wanted+language%3ALean&type=code&l=Lean)
declaration documents statements that have been identified as being useful, but that have not yet
been proven.
