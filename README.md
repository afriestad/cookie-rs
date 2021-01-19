# Difference from SergioBenitez/cookie-rs

This fork is exactly the same, except the branch v0.11 has been patched to cherry-pick commit ae6d4230cac4d3230ae848c76de0862835ecaa8e, which means it supports the latest version of `SameSite` and sets `SameSite=None` explicitly when you `.same_site(SameSite::None)`. No branches in this fork will receive more updates, with the sole exception of the `v0.11` branch in case a new `0.11.x` release is published before `rocket@0.5` releases.

_THIS IS A BREAKING CHANGE: previously v0.11 supported the previous draft where `None` was the default, and as such impicit. The new draft changed the default, meaning old browsers default to `SameSite=None` and new browsers default to `SameSite=Lax`._

[Make sure you understand what this means (MDN)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite).

## Use the patch

Add the following to your `Cargo.toml`:

```toml
[patch.crates-io]
cookie = { git = 'https://github.com/afriestad/cookie-rs', branch = 'v0.11'}
```

# Cookie

[![CI Status](https://github.com/SergioBenitez/cookie-rs/workflows/CI/badge.svg)](https://github.com/SergioBenitez/cookie-rs/actions)
[![Current Crates.io Version](https://img.shields.io/crates/v/cookie.svg)](https://crates.io/crates/cookie)
[![Documentation](https://docs.rs/cookie/badge.svg)](https://docs.rs/cookie)

A Rust library for parsing HTTP cookies and managing cookie jars.

# Usage

Add the following to your `Cargo.toml`:

```toml
[dependencies]
cookie = "0.14"
```

See the [documentation](http://docs.rs/cookie) for detailed usage information.

# License

This project is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in `cookie-rs` by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.
