<h1 align="center">
  <img src="logo.svg" alt="esque" width="120" /><br/>
  esque
</h1>

<p align="center">
  A statically typed, tensor-primitive systems language.<br/>
  Compiler is a single Go binary that emits ELF x86-64 Linux executables
  directly — no LLVM, no runtime to link.
</p>

<p align="center">
  <a href="https://esque-lang.github.io/esquec/"><strong>Docs</strong></a>
  &nbsp;·&nbsp;
  <a href="https://esque-lang.github.io/esquec/tour">Tour</a>
  &nbsp;·&nbsp;
  <a href="https://esque-lang.github.io/esquec/reference/">Reference</a>
</p>

## Projects

| Repo | What it is |
|------|------------|
| [**esquec**](https://github.com/esque-lang/esquec) | The compiler. Parse → typecheck → CEIR → MIR → x86-64 → ELF, all in one Go binary. |
| [**tree-sitter-esque**](https://github.com/esque-lang/tree-sitter-esque) | Tree-sitter grammar + highlight/locals/tags queries. Drops into Helix and nvim-treesitter. |
| [**esque-lsp**](https://github.com/esque-lang/esque-lsp) | Language server. Diagnostics, hover, completion, go-to-definition over LSP 3.17. |

## A taste

```esque
fn dot[N](x: f32[N], y: f32[N]) -> f32 = +/(x .* y)

fn main() -> i32 = {
    let a = [1.0, 2.0, 3.0];
    let b = [4.0, 5.0, 6.0];
    dot(a, b) as i32
}
```

Tensors are values — shapes are part of the type. Loop primitives
(`tabulate`, `scan`, `iterate_until`) and reduction operators (`+/`,
`-/`, `*/`, `//`) replace most uses of `for` and `while`.

## License

Everything under this org is [MIT](https://opensource.org/licenses/MIT)
© Donnis Moore.
