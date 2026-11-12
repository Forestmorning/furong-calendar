# 芙蓉历（Furong Calendar）自动更新仓库

这是「芙蓉历」Android App 的**自动在线更新分发仓库**，不是源码仓库。

## 这个仓库装什么
- `update.json`：版本信息文件。App 每次启动会拉取它，比对版本号，发现新版就提示下载安装。
- GitHub Release 里的 `furong-calendar-x.y.z-release.apk`：正式签名安装包。

## 朋友怎么装（首次安装）
两种方式任选其一，装的是**同一个 APK**，效果完全一样。

**方式 A：从 GitHub 直接下载（推荐，最省事）**
- 打开发布列表页（永远显示最新版）：
  https://github.com/Forestmorning/furong-calendar/releases
- 点进最新版本，在页面下方的 **Assets** 里点 `furong-calendar-x.y.z-release.apk` 即可下载。
- 想直接下当前版（v0.1.57），手机浏览器点这个固定链接：
  https://github.com/Forestmorning/furong-calendar/releases/download/v0.1.57/furong-calendar-0.1.57-release.apk
- 下载完成后点安装。**首次**从浏览器装 APK，安卓会弹出「允许该浏览器安装未知应用」，按提示开一下即可（仅此一次，以后免问）。

**方式 B：微信 / 邮件收发（备选）**
- 把最新 APK 文件直接发给朋友，点开安装即可（首次同样需允许「安装未知应用」）。

**装好以后**：打开 App 会自动检查更新，发现新版点一下就能下载安装，**全程无感、不丢数据**（同一把正式签名覆盖安装）。

## 开发者怎么发新版
1. 在工程里把 `app/build.gradle` 的 `versionCode` 升一位、`versionName` 改成新版本号，重新构建正式签名 APK。
2. 把新 APK 上传到本仓库的 Release（文件名用 ASCII，如 `furong-calendar-0.1.58-release.apk`）。
3. 更新 `update.json`：`versionCode` 填新值、`versionName` 填新版本号、`apkUrl` 填新 Release 附件地址、`size` 填新 APK 字节数、`note` 写更新说明。
4. 朋友下次打开 App 即自动收到更新。

## 备注
- App 内置的 AI 功能需要各自填写自己的 DeepSeek API Key（App 首次会提示）。
- 本仓库为公开仓库，仅为让 App 能免登录下载更新文件。
