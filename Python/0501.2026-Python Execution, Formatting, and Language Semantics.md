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
 

---

# Python 核心机制笔记（2026-01-05）

## 1. 字符串中的转义字符 vs 占位符
- 转义字符（如 `\n`、`\t`）在**编译时（词法分析阶段）**由 Python 解析器直接替换为实际字符。
- 占位符（如 `%s`、`{}`、f-string）在**运行时**进行替换：
  - `%` 继承自 C 的 printf 风格
  - f-string（Python 3.6+）使用现代格式迷你语言，`:` 分隔表达式与格式规格（如 `{weight:.4f}`）

## 2. Python 执行流程（CPython）
1. 源码 → 词法/语法分析 → AST  
2. 编译 → 字节码（code object，缓存为 .pyc）  
3. Python 虚拟机（PVM，栈式虚拟机）解释执行字节码  
4. 底层由 CPU 执行 PVM 的 C 机器码

## 3. 类型转换：int() 与 float() 的统一规则
- 两者都要求参数是数值或“纯净”数字字符串（仅含数字、可选正负号，float 允许一个小数点）。
- 任何额外字符（字母、空格、中文、货币符号等）都会导致转换失败。

## 4. 字符串与数值比较
- 同类型字符串可按 Unicode 码点逐字符比较（字典序）。
- 字符串与 int/float 不能直接比较，会抛 TypeError（Python 不做隐式转换）。

## 5. 逻辑运算符行为
- `and` / `or`：短路操作，返回**第一个决定结果的原始值**（可能是 0、''、None 等）。
- `not`：始终返回**布尔值** True 或 False。

## 6. 进制转换机制
- Python 不提供任意进制间的直接转换。
- 所有转换必须经过十进制整数（`int`）作为中介：
  - `int(string, base)` → 十进制
  - `bin()/oct()/hex()/format()` → 目标进制字符串
- 原因：实现简洁、代码复用、接口一致、性能足够，符合“显式优于隐式”哲学。

## 今日思考题（可用于与粉丝互动）

1. 你觉得 Python 把 `and`/`or` 设计成返回原始值而不是布尔值，是便利还是潜在陷阱？在实际项目中你遇到过相关坑吗？
2. 如果让你重新设计 Python 的进制转换 API，你会加入“任意进制直接互转”的内置函数吗？为什么？
3. 在学习一门语言时，你更倾向先掌握表层语法，还是像今天这样深挖底层机制？哪种方式让你进步更快？

