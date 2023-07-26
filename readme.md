# 500行代码学会Rust
[English (TODO)]()| 中文

- RTD (Rust ToDo) 是一个用500行（不包括空行/注释/长行折断显示）Rust 代码编写的todo app命令行工具。
- RTD同时也是一个教程，旨在通过实践学习Rust。
- Learning by doing!

（目录）

---

## 你能从RTD学到什么？

#### 通过[500行代码学会Rust(TODO)]()教程，一步步从零构建该项目，你将学会：
  - Rust常用语法
  - Rust模块系统(`package`/`binary crate`/`library crate`/`mod`/`pub`/`use`)
  - Rust所有权模型(伯恩斯坦条件)
  - Rust错误/空值处理(`Result`/`Option`)
  - Rust模式匹配(`if let` , `match` ...)
  - Rust单元测试
  - Rust文件读写(`File Seek`/`Buffed File I/O`)
  - Rust操作环境变量
  - Rust命令行参数解析
  - 分层抽象(数据存储层/模型映射层/数据模型层/业务逻辑层/应用接口层/用户接口层)
  - 从零手写序列化/反序列化
  - 实现回收站功能（虚拟化概念）

###### 架构图

![rtd_arch_zh](Tutorial/doc/img/rtd_arch_zh.svg)

###### 存储
使用一个本地文件 `$HOME/.rtd.csv` 存储所有数据

![data_storage](Tutorial/doc/img/csv.png)

#### 完成该教程或直接安装RTD，你将得到:
  - 极其轻量级且简洁的todo命令行应用
  - 跨平台，Rust项目优秀的构建系统天然支持跨平台
  - 安全，支持回收站，完全本地，不联网，无数据库
  - 所有数据存储仅使用一个本地csv文件，可以通过复制csv文件来在不同机器间切换

---
如果你喜欢我的教程，别忘了给我点个赞哦～
---

## 准备

- Rust 天然跨平台，本项目在 `linux` 环境构建测试，`Windows`/`MacOS` 同样支持，根据自身操作系统选择下载对应 `Cargo` 即可。
- `Cargo` Rust 包管理和构建工具, 可通过[官网](https://www.rust-lang.org/tools/install)`rustup`一行命令直接安装，接下来的事情，它会帮你全搞定，很可爱，不是吗？

## 安装

```bash
git clone https://github.com/cuppar/rtd.git
cargo install --path rtd
```

## 使用

#### 查看帮助说明
```bash
rtd -h
rtd --help
```

![rtd_help_summary](Tutorial/doc/img/rtd_help_summary.png)
![rtd_help](Tutorial/doc/img/rtd_help.png)

#### 添加一个todo
```bash
rtd -a <item-name>
rtd --add <item-name>
```

![rtd_add](Tutorial/doc/img/rtd_add.png)

#### 列出所有未完成的todo
```bash
rtd
rtd -l
rtd -l uncompleted
rtd --list
rtd --list uncompleted
```

![rtd_list_uncompleted](Tutorial/doc/img/rtd_list_uncompleted.png)

#### 完成一个todo
```bash
rtd -c <item-id>
rtd --complete <item-id>
```

![rtd_complete_item](Tutorial/doc/img/rtd_complete_item.png)

#### 列出所有已完成的todo
```bash
rtd -l completed
rtd --list completed
```

![rtd_list_completed](Tutorial/doc/img/rtd_list_completed.png)

#### 标记一个todo为未完成
```bash
rtd -u <item-id>
rtd --uncomplete <item-id>
```

![rtd_uncomplete_item](Tutorial/doc/img/rtd_uncomplete_item.png)

#### 把一个todo扔进回收站
```bash
rtd -d <item-id>
rtd --delete <item-id>
```

![rtd_delete_item](Tutorial/doc/img/rtd_delete_item.png)

#### 列出所有回收站的todo
```bash
rtd -l deleted
rtd --list deleted
```

![rtd_list_deleted](Tutorial/doc/img/rtd_list_deleted.png)

#### 从回收站恢复一个todo
```bash
rtd -r <item-id>
rtd --restore <item-id>
```

![rtd_restore_item](Tutorial/doc/img/rtd_restore_item.png)

#### 物理销毁一个todo
```bash
rtd --destroy <item-id>
```

![rtd_destroy_item](Tutorial/doc/img/rtd_destroy_item.png)

#### 清空回收站
```bash
rtd --destroy-deleted
```

![rtd_destroy_deleted](Tutorial/doc/img/rtd_destroy_deleted.png)

#### 列出所有todo
```bash
rtd -l all
rtd --list all
```

![rtd_list_all](Tutorial/doc/img/rtd_list_all.png)

#### 清空所有todo
```bash
rtd --clear
```

![rtd_clear](Tutorial/doc/img/rtd_clear.png)

