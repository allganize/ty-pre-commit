# ty-pre-commit

[![Ty](https://img.shields.io/pypi/v/ty.svg)](https://pypi.org/project/ty/)
[![image](https://img.shields.io/pypi/v/ty/0.0.1a25.svg)](https://pypi.python.org/pypi/ty)
[![image](https://img.shields.io/pypi/l/ty/0.0.1a25.svg)](https://pypi.python.org/pypi/ty)
[![image](https://img.shields.io/pypi/pyversions/ty/0.0.1a25.svg)](https://pypi.python.org/pypi/ty)
[![Actions status](https://github.com/astral-sh/ty-pre-commit/workflows/main/badge.svg)](https://github.com/astral-sh/ty-pre-commit/actions)

A [pre-commit](https://pre-commit.com/) hook for [Ty](https://github.com/astral-sh/ty), an extremely fast Python type checker written in Rust.

Distributed as a standalone repository to enable installing Ty via prebuilt wheels from
[PyPI](https://pypi.org/project/ty/).

> **Warning**: Ty is currently in preview and not ready for production use. Expect bugs and missing features.

### Using Ty with pre-commit

To run Ty's type checker via pre-commit, add the following to your `.pre-commit-config.yaml`:

```yaml
repos:
- repo: https://github.com/allganize/ty-pre-commit
  # Ty version.
  rev: v0.0.1a25a24a23a22a21a20
  hooks:
    # Run the type checker.
    - id: ty-check
```

To run Ty with additional arguments:

```yaml
repos:
- repo: https://github.com/allganize/ty-pre-commit
  # Ty version.
  rev: v0.0.1a25a24a23a22a21a20
  hooks:
    # Run the type checker with verbose output.
    - id: ty-check
      args: [ --verbose, --output-format=full ]
```

To run only on specific file types:

```yaml
repos:
- repo: https://github.com/allganize/ty-pre-commit
  # Ty version.
  rev: v0.0.1a25a24a23a22a21a20
  hooks:
    # Run the type checker.
    - id: ty-check
      types_or: [ python, pyi ]
```

Ty is a type checker and can be run alongside other tools like Black, isort, and Ruff for formatting and linting. Since Ty only performs type checking, it doesn't conflict with formatters and can be placed anywhere in your pre-commit hook chain.

## License

ty-pre-commit is licensed under either of

- Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or <https://www.apache.org/licenses/LICENSE-2.0>)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or <https://opensource.org/licenses/MIT>)

at your option.

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in ty-pre-commit by you, as defined in the Apache-2.0 license, shall be
dually licensed as above, without any additional terms or conditions.
