# 芙蓉历（Furong Calendar）自动更新仓库

这是「芙蓉历」Android App 的**自动在线更新分发仓库**，不是源码仓库。

## 这个仓库装什么
- `update.json`：版本信息文件。App 每次启动会拉取它，比对版本号，发现新版就提示下载安装。
- GitHub Release 里的 `furong-calendar-x.y.z-release.apk`：正式签名安装包。

## 朋友怎么装
1. 第一次：把最新 APK 发给朋友（微信 / 邮件），点开安装即可（首次需允许「安装未知应用」）。
2. 以后：打开 App 会自动检查更新，点一下就能下载安装，**全程无感、不丢数据**（同一把正式签名覆盖安装）。

## 开发者怎么发新版
1. 在工程里把 `app/build.gradle` 的 `versionCode` 升一位、`versionName` 改成新版本号，重新构建正式签名 APK。
2. 把新 APK 上传到本仓库的 Release（文件名用 ASCII，如 `furong-calendar-0.1.58-release.apk`）。
3. 更新 `update.json`：`versionCode` 填新值、`versionName` 填新版本号、`apkUrl` 填新 Release 附件地址、`size` 填新 APK 字节数、`note` 写更新说明。
4. 朋友下次打开 App 即自动收到更新。

## 备注
- App 内置的 AI 功能需要各自填写自己的 DeepSeek API Key（App 首次会提示）。
- 本仓库为公开仓库，仅为让 App 能免登录下载更新文件。
