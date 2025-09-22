# 测试用例编译记录

## 编译选项说明
- `-g`: 编译源文件并得到IR（文本格式.ll）
- `-fno-discard-value-names`: 保留变量名
- `-Xclang` + `-disable-O0-optnone`: 开启函数内部优化（在O0选项下激活内部函数优化）
- `opt -S -p=mem2reg`: 优化并获得更紧凑的IR

## 文件处理记录

| 源文件 | 编译选项组合 | 生成的LLVM文件 |
|--------|-------------|----------------|
| `andersen.c` | 基础选项 + `-g` + `-fno-discard-value-names` + `-Xclang` + `-disable-O0-optnone` | `andersen.ll` |
| `branch.c` | 基础选项 + `-fno-discard-value-names` + `-Xclang` + `-disable-O0-optnone` | `branch.ll` |
| `control-flow.c` | 基础选项 + `-g` + `-fno-discard-value-names` | `control-flow.ll` |
| `example.c` | 基础选项 + `-g` + `-Xclang` + `-disable-O0-optnone` | `example.ll` |
| `interprocedural.c` | 基础选项 + 所有优化 | `interprocedural.ll` |
| `swap.c` | 基础选项 | `swap.ll` |
