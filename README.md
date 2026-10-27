# OpenWrt-AutoBuild（精简 x86_64）

基于本仓库原有的 GitHub Actions 自动编译框架，当前默认仅保留 **Lean x86_64** 固件目标，尽量沿用上游脚本结构。

## 固件内容

- **OpenClash**：唯一代理客户端；编译脚本会尝试下载并内置 OpenClash Meta/Mihomo 内核。
- **Argon**：LuCI 主题。
- **简体中文 LuCI**：启用简体中文语言并将默认界面语言设为中文。
- 不编译 Nikki、Passwall、Passwall2、SSR-Plus、V2Ray 服务端、Trojan、NaiveProxy、Brook 等其他代理组件。
- 关闭其他额外 LuCI 插件，保留基础系统组件和原有 x86_64 镜像构建流程。

## 如何编译

1. 打开仓库的 [Actions](../../actions)。
2. 选择 **编译OpenWrt固件**。
3. 点击 **Run workflow**，保持 `Lean_x86_64` 勾选。
4. 等待工作流完成，在对应运行记录的 Artifacts 或 [Releases](../../releases) 中查看输出（具体取决于工作流中的上传/发布设置）。

当前已关闭定时编译，避免未经手动操作消耗 Actions 额度。

## 上游来源

- [Lean](https://github.com/coolsnowwolf/lede)
- [db-one packages](https://github.com/db-one/dbone-packages)
- [P3TERX Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt)

> 注意：当前仅完成仓库脚本和配置修改，尚未实际运行完整编译；首次编译结果仍需通过 GitHub Actions 日志验证。