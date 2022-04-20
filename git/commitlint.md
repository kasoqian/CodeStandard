---
description: 基于git commit时message的规范约束
---

# commit

## 介绍

Git是一个免费的、开源的分布式项目版本控制系统，旨在以快速高效的方式处理从小型到大型的所有项目。

git commit会对代码更改后进行快照，提交一个commit作为一个节点，意味达到某一“安全”的版本。除非开发者手动操作，否则git永远不会主动修改历史commit。

本文介绍有关于commit中所提供的相关表述规范，使其符合开发规范。

## 开始使用

如果您还没有安装git，可以点此[下载Git](https://git-scm.com/downloads)。

下载完客户端后，在命令行输入git并敲击回车，显示`command not found`则为安装失败。如显示下列指引则为成功，

```
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]
```

## 基本用法

**案例**

```git 
feat(user.tsx): add user login module(#9527)
```

  1. `feat`，表示提交的类型，统一小写；
  2. `user.tsx`，为模块名或文件名，选用；
  3. `:`，为半角，且后面需补加一个空格;
  4. `add user login module`，简要描述提交内容；
  5. `#9527`，为模块编号，选用。


### 常用类型

#### `feat`
**描述**

实现某一功能或特性。

```
feat(模块?)：实现某一功能的描述(#功能的需求号?)
```

**案例**

```
feat: improve template expression error message    // vue写法
```

#### `fix`

**描述**

修复 bug，通常在尾部追加bug号。

```
fix(模块?)：修复某一功能的描述(#bug号)
```

**案例**

```
fix(security) upgrade lodash.template (#10257)    // vue写法 
```


#### `docs`

**描述**

更新文档相关的内容。

```
docs(模块?)：更新了一下文档(#文档号?)
```

**注意**

在vue中主要采用`chore`来修改文档，而用docs较少。

```
docs: fix link to point to ModuleOptions lines (#10531)    // vue写法
```

#### `chore`

**描述**

常规事务相关的操作，无关核心代码。常见包括有修改package.json，处理ci/cd，定时导出日志等。

```
chore(模块?): 常规事务的操作(#事务号?)
```

**案例**

```
chore(readme): svg image (#11078) [ci skip]    // vue写法
```

#### `refactor`

**描述**

单纯的代码重构，未改变结构任何功能。

```
refactor(模块?)：重构了某功能的组织形式(#重构需求号)
```

**案例**

```
refactor: improve option type check warnings    // vue写法
```

### 不常用类型

#### `build`

**描述**

主要目的是修改项目构建系统(例如 glup，webpack，rollup 的配置等)的提交。

```
build(模块?): 构建某一个工具或板块(#构建号)
```

**案例**

```
build(deps): bump eslint-utils from 1.3.1 to 1.4.2 (#10630)    // vue写法 
```

#### `ci`

**描述**

修改项目继续集成相关流程。

```
ci(模块)：主要目的是修改项目继续集成流程(例如 Travis，Jenkins，GitLab CI，Circle等)的提交
```

#### `UI`

**描述**

更新 UI 样式相关的内容。

```
UI(模块?)：修改了某一处样式(#需求号?)
```

#### `locale`

**描述**

多语言相关内容。

```
locale(en?)：完成某个页面的国际化内容(#需求号?)
```


#### `perf`

**描述**

性能优化。

```
perf(模块?)：优化了某方面的性能(#需求号?)
```

**案例**

```
perf: skip scoped slots normalization when possible     // vue写法
```


#### `test`

**描述**

新增测试用例或是更新现有测试。

```
test(模块?)：新增测试用例或是更新现有测试(#需求号?)
```

**示例**

```
refactor: improve test case    // vue写法
```

#### `revert`

**描述**

回滚某个更早之前的提交。

```
revert(模块?)：回滚某个更早之前的提交(#需求号?)
```

## 参考资料

1. [conventionalcommits](https://www.conventionalcommits.org/zh-hans/v1.0.0/)
2. [Git commit](https://www.atlassian.com/git/tutorials/saving-changes/git-commit)
3. [vue](https://github.com/vuejs/vue/commits/dev?after=6aa11872c88481dfa2da151536317176c48f226c+279&branch=dev)