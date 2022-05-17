[![Workflow Status](https://github.com/M4tsuri/totp_embed/actions/workflows/rust.yml/badge.svg)](https://github.com/M4tsuri/totp_embed/actions/workflows/rust.yml)
[![](https://img.shields.io/crates/v/totp_embed.svg)](https://crates.io/crates/totp_embed)

# totp_embed

This is a fork of original [totp-lite](https://github.com/fosskers/totp-lite) with some changes on API and added support for `no_std`.

```rust
fn totp1_tests() {
    let secret: &[u8] = b"12345678901234567890";
    assert_eq!(20, secret.len());
    let pairs = vec![
        (94287082, 59),
        (07081804, 1111111109),
        (14050471, 1111111111),
        (89005924, 1234567890),
        (69279037, 2000000000),
        (65353130, 20000000000),
    ];
    
    pairs.into_iter().for_each(|(expected, time)| {
        assert_eq!(expected, totp::<Sha1>(secret, time));
    });
}
```

See [totp-lite](https://github.com/fosskers/totp-lite) for more details.

License: MIT
