# Python - uv创建虚拟环境


```bash
uv venv  # 默认创建在 .venv 目录
```

2. **激活虚拟环境**：
    - Windows: `.venv\Scripts\activate`
    - Linux/macOS: `source .venv/bin/activate`

3. **安装包**：
```bash
uv pip install <包名>
```

4. **使用 `uv run` 运行脚本**（自动使用环境）：
```bash
uv run main.py
```

5. **查看已安装包**：
```bash
uv pip list
```


很多 AI 项目在 **Docker 里不用 venv**，不是偷懒，而是因为 **Docker 本身已经是一个更强的隔离层**。

一句话结论：

> **Docker = 操作系统级虚拟环境**  
> **venv = Python级虚拟环境**

当你已经有 Docker 时，再用 venv 往往是 **重复隔离（double isolation）**。
