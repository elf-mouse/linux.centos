## 批量注释与反注释

### ① 块选择模式

__插入注释：__

1. 用`v`进入virtual模式
2. 用`上下键`选中需要注释的行数
3. 按`Control+v`（win下面`ctrl+q`）进入列模式
4. 按大些`I`进入插入模式，输入注释符`#`或者是`//`，然后立刻按下`ESC`（两下）

__取消注释：__

1. `Ctrl + v` 进入块选择模式
2. 选中你要删除的行首的注释符号，注意// 要选中两个
3. 选好之后按`d`即可删除注释

### ② 替换命令

__批量注释：__

使用下面命令在指定的行首添加注释：`:起始行号,结束行号s/^/注释符/g`

__取消注释：__

`:起始行号,结束行号s/^注释符//g`

__实例演示：__

在27 - 30行添加 // 注释

```
:27,30s#^#//#g
```

在27 - 30行删除 // 注释

```
:27,30s#^//##g
```

在10 - 20行添加 # 注释

```
:10,20s/^/#/g
```

在10 - 20行删除 # 注释

```
:10,20s/^/#/g
```

> 注意例子中正则的分割符使用的是相反的符号，如果匹配// 那么使用 #作分隔符这样不需要对/作转义处理，节省输入次数。