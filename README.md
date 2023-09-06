# Hinode Module - Bootstrap

<!-- Tagline -->
<p align="center">
    <b>A Hugo module to add the Bootstrap toolkit to your Hinode site</b>
    <br />
</p>

<!-- Badges -->
<p align="center">
    <a href="https://gohugo.io" alt="Hugo website">
        <img src="https://img.shields.io/badge/generator-hugo-brightgreen">
    </a>
    <a href="https://gethinode.com" alt="Hinode theme">
        <img src="https://img.shields.io/badge/theme-hinode-blue">
    </a>
    <a href="https://github.com/gethinode/mod-bootstrap/commits/main" alt="Last commit">
        <img src="https://img.shields.io/github/last-commit/gethinode/mod-bootstrap.svg">
    </a>
    <a href="https://github.com/gethinode/mod-bootstrap/issues" alt="Issues">
        <img src="https://img.shields.io/github/issues/gethinode/mod-bootstrap.svg">
    </a>
    <a href="https://github.com/gethinode/mod-bootstrap/pulls" alt="Pulls">
        <img src="https://img.shields.io/github/issues-pr-raw/gethinode/mod-bootstrap.svg">
    </a>
    <a href="https://github.com/gethinode/mod-bootstrap/blob/main/LICENSE" alt="License">
        <img src="https://img.shields.io/github/license/gethinode/mod-bootstrap">
    </a>
</p>

## About

![Logo](https://raw.githubusercontent.com/gethinode/hinode/main/static/img/logo.png)

Hinode is a clean blog theme for [Hugo][hugo], an open-source static site generator. Hinode is available as a [template][repository_template], and a [main theme][repository]. This repository maintains a Hugo module to add the [Bootstrap toolkit][bootstrap] to a Hinode site. Visit the Hinode documentation site for [installation instructions][hinode_docs].

## Notes

### Vendor files

Hugo uses Go Modules under the hood. The top-level `/vendor` directory has a special meaning and is deleted from the release bundle after downloading. Unfortunately the algorithm is a bit too agressive and removes the `scss/modules/bootstrap/vendor` from the Bootstrap repository too.

This modules uses a workaround to mount the folder from the project itself. The concerned file `_rfs.scss` is copied from the npm release assets by running the npm script `update:vendor:step1`. See https://github.com/gohugoio/hugo/issues/6945 for more details.

### Dart support

When transpiling with Dart Sass, use the file `assets/scss/bootstrap-dart.scss` an entrypoint instead of `assets/scss/bootstrap.scss`. The former file includes modifications to address several deprecation warnings. Run the npm command `update-scss` to recreate the modified files, which are derived from the Bootstrap source files. The script is **not compatible with Windows**, due to the different handling of double quotes on this Operating System.

<!-- MARKDOWN LINKS -->
[hugo]: https://gohugo.io
[hinode_docs]: https://gethinode.com
[bootstrap]: https://getbootstrap.com
[repository]: https://github.com/gethinode/hinode.git
[repository_template]: https://github.com/gethinode/template.git
