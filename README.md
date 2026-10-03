# Nil phar 自动打包

自动打包 PHP 项目为 phar 文件。

doctrine/dbal 暂时锁定为 4.4.x 版本

## 手动打包（单 URL）

在 Actions → **Manual Build Phar (URL)** 中触发，只需填写一个组合 JSON 的 URL（包含 `composer` 与 `nil` 两个段，参考 `src/p/markdown.json`）：

```
https://raw.githubusercontent.com/php-nil/phar-auto/main/src/p/markdown.json
```

工作流会自动下载并拆分为 `composer.json` / `nil.json`，包名取自 `.nil.packages` 的第一个键（如 `markdown`），最终产出单个制品 `<包名>.zip`（如 `markdown.zip`），内含 `<包名>.phar` 与 `vendor/` 目录。