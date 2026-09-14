# Chrome 可执行文件

Google Chrome 稳定版（Windows x64）便携包，供 CZL Browser 作为"标准 Chrome"内核下载使用。

## 自动更新

`.github/workflows/sync-chrome-stable.yml` 每天北京时间 09:00 运行：

1. 读取 [Bush2021/chrome_installer](https://github.com/Bush2021/chrome_installer) 的 `data.json`，获取最新稳定版版本号、Google 官方下载地址和 SHA256；
2. 只从 Google 官方域名（dl.google.com 等）下载离线安装包，并校验 SHA256 和文件大小；
3. 解压出 `Chrome-bin/`，重新打包为 `Chrome-bin.zip`，连同 `Chrome-bin.zip.sha256` 发布为 Release（tag 为版本号）。

二进制文件完全来自 Google，第三方仓库只提供元数据。Actions 页面可以手动触发（勾选 `force` 可重新打包已存在的版本）。
