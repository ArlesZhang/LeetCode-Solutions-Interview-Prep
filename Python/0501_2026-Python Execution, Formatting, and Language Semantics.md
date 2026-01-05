# Python Execution, Formatting, and Language Semantics — Daily Notes

## 1. Python Execution Model (CPython)

Python is **not** “line-by-line interpreting source code”.
Its real execution pipeline is:

```
.py source
 → Lexing (tokenization, escape sequence handling)
 → Parsing (syntax analysis)
 → AST (Abstract Syntax Tree)
 → Bytecode compilation (.pyc)
 → Python Virtual Machine (stack-based execution)
```

Key takeaways:

* Python is **compile-then-execute**, not pure interpretation.
* Escape characters like `\t`, `\n` are handled **during lexing**.
* f-strings are parsed into special AST nodes (`JoinedStr`, `FormattedValue`).

---

## 2. Escape Characters vs Placeholders

Although both appear inside quotes, they belong to **different execution layers**:

| Feature           | Happens at       | Nature                      |
| ----------------- | ---------------- | --------------------------- |
| `\t`, `\n`        | Lexical analysis | Source-level translation    |
| `%s`, `%.2f`      | Runtime          | String formatting DSL       |
| f-string `{expr}` | Parse + runtime  | Embedded Python expressions |

Important:

* Escape sequences are **not strings** at runtime; they are already translated.
* f-string expressions are **real Python expressions**, evaluated at runtime.

---

## 3. `%` Formatting vs f-String Formatting

These are **two independent systems** with different design goals.

### `%` formatting (C heritage)

```python
'%.2f' % x
```

* `.2f` → **fixed decimal places**
* Syntax comes from `printf`

### f-string / `format()` (Python-native)

```python
f'{x:.4}'
```

* `.4` → **total significant digits**
* `.4f` → fixed decimal places
* Grammar: `{expression : format_spec}`

They cannot be unified because:

* `%` is an **operator**
* f-string is **syntax-level string interpolation**

---

## 4. `not` vs `and / or`

### `not`

```python
not x
```

* Always returns `bool`
* Semantics: `not bool(x)`

### `and / or`

```python
x and y
x or y
```

* Return **operands themselves**
* Designed as value-selecting, short-circuit operators

This distinction is **intentional language design**, not inconsistency.

---

## 5. Numeric Bases in Python

English terms:

* Binary (base-2)
* Octal (base-8)
* Decimal (base-10)
* Hexadecimal (base-16)

### Conversion rule (very important):

> **All base conversions go through `int`**

```python
int('1010', 2)   → decimal
format(10, 'o') → octal
```

There is **no direct base-to-base conversion**, because:

* Python integers have **no intrinsic base**
* Base is only a *representation*, not a value property

---

## Three Thoughts to Reflect On / Discuss with Readers

1. **Python’s “simplicity” often comes from hiding compiler stages, not removing them**
   — How does this influence how beginners and system programmers perceive the language?

2. **Why does Python choose semantic clarity (`not` always returns `bool`) over uniformity (`and/or`)?**
   — What does this say about Python’s philosophy compared to C-like languages?

3. **If integers have no base, should programmers think more in “values” and less in “representations”?**
   — How does this mindset transfer to systems, compilers, and IR design?


If you want, I can next help you:

* Turn this into a **blog post**
* Add **bytecode / AST diagrams**
* Or align it with a **compiler-learning series** for your GitHub audience
