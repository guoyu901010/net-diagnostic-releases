# Net Diagnostic 安装包

本仓库只存放编译好的安装包，供 Net Diagnostic 桌面端检查更新与下载使用。源码仓库是私有的。

每个 Release 附三个文件：

- `NetDiagnostic-<版本>-x64.msi`：每用户安装包（无需管理员）
- `net-diagnostic.exe`：免安装单文件
- `SHA256SUMS.txt`：两个产物的 SHA256 与版本信息

## 校验下载

```powershell
Get-FileHash .\NetDiagnostic-<版本>-x64.msi -Algorithm SHA256
```

与 `SHA256SUMS.txt` 中对应行比对。

## 更新检查

应用默认读取本仓库的 `releases/latest`：

```
https://api.github.com/repos/guoyu901010/net-diagnostic-releases/releases/latest
```

只比较版本号并跳转发布页，不自动下载或安装。

## 安全说明

安装包未做代码签名，Windows 会提示"未知发布者"。请以本仓库的 SHA256SUMS 为准核对文件完整性。