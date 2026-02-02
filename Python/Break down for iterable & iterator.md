Python 中延迟执行（Lazy Evaluation）、迭代器协议与流式&管道式处理的思想，是 Python 高效处理大数据、函数式编程风格的核心之一。

> 先区分几个概念：可迭代对象（`iterable`）、迭代器（iterator）、迭代器的__next__方法

```
容器 (Container) → 可迭代对象 (Iterable) → 迭代器 (Iterator) → 生成器 (Generator)
```

调用`__iter__`方法会得到：迭代器(iterator)
1. `__iter__`是一个魔法方法，当调用 `iter` 函数时，`__iter__`会自动调用。
2. 可迭代对象.`__iter__`() 等价于： `iter`(可迭代对象)。
3. 如果`iter(obj)`能得到一个迭代器(iterator)，那obj就是可迭代对象。

---

**迭代器协议**：一个对象如果同时满足如下规范，那该对象就是一个迭代器
1. 能被`iter()`接受。
2. 能被next()一步一步取值。
迭代器是一次性的，状态只会向前推进，且不会自动重置（迭代器在遍历的过程中会被“消耗”）。

`iterable`(obj) 身上有`__iter__` 方法 -> `obj.__iter__`  -> 得到 iterator (`__iter__`  `__next__` )
```text
obj                                   
 └── obj.__iter__()   等价于（iter(obj)）
       └── 返回 iterator            
            ├── iterator.__iter__()    （iter(iterator)）
            │     └── 返回 iterator 本身
            │
            └── iterator.__next__()    （next(iterator)）
                  ├── 根据内部状态（指针 / 游标）
                  ├── 返回下一个元素
                  │
                  └── 若元素耗尽
                        └── 抛出 StopIteration
```
