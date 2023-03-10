
Version 0.9.1 (2023-03-13)
* Add CHANGES.md
* `virtual` project skeletons (inherited by all):
  * new field `docker-alpine-packages` to install more packages in the alpine image for
    static builds
  * fix opam packages paths in Makefile

Version 0.9.0 (2023-03-06)
* Only available with `drom>=0.9`
* `virtual` project skeletons (inherited by all):
    * Add `readme-trailer` field, appended into README.md and
      `docs/index.html` (after `md-to-html` encoding)
    * `docs/index.html`: remove `!{random}` and use
       `!{docs/style.css:>:read:md5}` instead (reading the file is postponed
        after its generation)
    * Github workflows:
      * new field `git-main-branch` to replace `master`
      * new field `build-scripts` to list script outside of `scripts/` that
        should be converted for Windows (add `src/PROJECT/linking-flags.sh`
	for example)
      * new field `github-workflow-after-test` to be run after tests (for
        example to upload artifacts in case of failure)
      * new field `github-workflow-trailer` to append extra steps
    * Add `scripts/static-build.sh` to build a static version in a docker
      alpine
      * use `ocamlpro/ocaml:4.13` by default
      * new field `docker-alpine-image` to change this image
* `program` package skeletons (inherited by `driver`):
  * Add `static-clibs`, `static-alpine-clibs`, `static-macos-clibs` fields
    for static linking
* Licenses:
  * Make `OCAMLPRO-NON-COMMERCIAL` SPDX compatible (to silent an `opam` warning)


Version 0.8.0 (2023-03-06)
* Initial version, compatible with `drom.0.8.0` skeletons
