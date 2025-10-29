# `compose_yml`: Support for working with `docker-compose.yml` files

[![Latest version](https://img.shields.io/crates/v/compose_yml.svg)](https://crates.io/crates/compose_yml) [![License](https://img.shields.io/crates/l/compose_yml.svg)](https://creativecommons.org/publicdomain/zero/1.0/) [![Build Status](https://travis-ci.org/faradayio/compose_yml.svg?branch=master)](https://travis-ci.org/faradayio/compose_yml) [![Build status](https://ci.appveyor.com/api/projects/status/ltvu7d7qb1iw7dh6/branch/master?svg=true)](https://ci.appveyor.com/project/faradayio/compose-yml/branch/master) [![Documentation](https://img.shields.io/badge/documentation-docs.rs-yellow.svg)](https://docs.rs/compose_yml/) [![Gitter](https://badges.gitter.im/faradayio/cage.svg)](https://gitter.im/faradayio/cage?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

**This is a work in progress!** Most of `services:` is supported, but I'm
still refining the APIs as higher-level tools get build around this.

## Goals

`docker-compose.yml` is a very useful format, but it's hard to parse and
transform correctly. This library aims to offer:

- High-level, type-safe APIs for anything you can find in a
  `docker-compose.yml` file.
- Parsing of individual string fields into real objects.
- Support for working with strings that might contain variable
  interpolations, and leaving them unparsed when necessary.
- Canonical representations of fields which may have multiple formats.
- Easy updates when `docker-compose.yml` gets extended.

## Building

You can build this library using stable Rust version 1.11. But if you want
to develop it, you will get _much_ better error messages using a nightly
build of Rust.

```sh
# Install Rust stable and nightly using rustup.
curl -sSf https://static.rust-lang.org/rustup.sh | sh
rustup toolchain install nightly

# Build unit tests using nightly Rust.
rustup run nightly cargo test --no-default-features --features unstable
```

## License

This library is in the public domain as described by `LICENSE.txt`, except for the files `src/v2/validate/config_schema_v2.*.json`, which are copyright Docker, Inc., and distributed under the Apache License, version 2.0.

## Sponsor

Part of the work on [`compose_yml`][compose_yml] has been generously
sponsored by [Faraday][] for use in their [`cage`][cage] tool, which is
designed to go beyond `docker-compose` and provide support for large,
multi-pod apps.

[Faraday]: http://www.faraday.io/
[cage]: https://github.com/faradayio/cage
[compose_yml]: https://github.com/faradayio/compose_yml
