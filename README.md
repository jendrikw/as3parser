# ActionScript 3 Parser

<p align="center">
  <a href="https://lib.rs/crates/as3_parser">
    <img src="https://img.shields.io/badge/lib.rs-green">
  </a>
  <a href="https://docs.rs/as3_parser">
    <img src="https://img.shields.io/badge/Rust%20API%20Documentation-gray">
  </a>
</p>

ActionScript 3 parser in the Rust language.

[Online demo](https://hydroper.github.io/as3parser/demo)

## Documentation

[Getting started](docs/getting-started.md)

[Working with diagnostics](docs/diagnostics.md)

[Working with interpolated ActionScript](docs/interpolation.md)

[Working with MXML](docs/working-with-mxml.md)

[Standards and Documents](docs/standards.md)

[New Syntax](docs/new-syntax.md)

[Processing Deviations](docs/processing-deviations.md)

## Verifier

ActionScript execution consists of parsing, verification, and evaluation. Verification can be performed ahead of time, as is already done by the existing initial compilers of the language (ASC 2 and Apache Flex's MXML compiler), reporting errors and warnings, deriving a control flow graph for every activation, and attaching symbols to syntactic nodes. This project might be integrated with a verifier in the future.

## CSS parsing

MXML supports a subset of CSS.

- [ ] Define tree structures
- [ ] Parse a style sheet

Conform to Apache Royale sources:

- [CSS.g](https://github.com/apache/royale-compiler/blob/develop/compiler/src/main/antlr3/org/apache/royale/compiler/internal/css/CSS.g)
- [CSSTree.g](https://github.com/apache/royale-compiler/blob/develop/compiler/src/main/antlr3/org/apache/royale/compiler/internal/css/CSSTree.g)

## License

Apache License 2.0, copyright 2024 Hydroper
