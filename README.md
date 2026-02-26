# tg-arceos-tutorial

`tg-arceos-tutorial` 是一个集合 crate，用于把 `app-*` 教学 crate 的源码打包到一个压缩包里，便于通过 `cargo clone` 后离线解包恢复完整目录。

## 使用方式

```bash
cargo clone tg-arceos-tutorial
cd tg-arceos-tutorial
bash scripts/extract_crates.sh
```

解包后会在当前目录生成以下 15 个 crate 目录：

- `app-childtask`
- `app-collections`
- `app-fairsched`
- `app-guestaspace`
- `app-guestmode`
- `app-guestmonolithickernel`
- `app-guestvdev`
- `app-helloworld`
- `app-lazymapping`
- `app-loadapp`
- `app-msgqueue`
- `app-readblk`
- `app-readpflash`
- `app-runlinuxapp`
- `app-userprivilege`

进入任意 crate 目录即可独立构建/运行。

## 维护者：重新生成 bundle

在包含 `app-*` 目录的路径中执行：

```bash
cd tg-arceos-tutorial
SOURCE_ROOT=.. bash scripts/compress_crates.sh
```

将生成：

- `bundle/apps.tar.gz`

该压缩包会被 `Cargo.toml` 的 `include` 字段打包进发布产物。
