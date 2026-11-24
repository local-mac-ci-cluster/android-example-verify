# AndroidExample — Macrunara Android CI Example

A minimal Android app (single Activity, Java, no dependencies) demonstrating CI on **Macrunara** — M4 Mac mini (Apple Silicon) runners for GitHub Actions.

Works immediately after fork: the node image ships JDK 17 (temurin) + Android SDK (API 35, build-tools 35.0.0, NDK 27) with licenses pre-accepted — no setup steps, no secrets.

## How It Works

1. Install the **Macrunara** App from GitHub Marketplace into your organization.
2. Fork this repository (or copy `.github/workflows/android-gradle.yml` into your own repo).
3. Push to `main` — the job runs on a Macrunara M4 node and uploads the debug APK as an artifact.

The workflow uses the standard three-label form `runs-on: [macos, arm64, macrunara]`. Do **not** use `self-hosted` or `macos-latest` — the job would queue forever without an error.

## Repository Layout

```
app/                        # single-Activity Java app (assembleDebug → APK)
.github/workflows/          # android-gradle.yml (from macrunara/quickstart templates)
gradle/wrapper/             # Gradle 8.9 (bin)
```

## Customizing

- Swap the Gradle task: `:app:assembleRelease` for a release APK, `:app:bundleRelease` for an AAB.
- Add unit tests: `./gradlew testDebugUnitTest --no-daemon`.
- More templates (iOS / Flutter / React Native): [macrunara/quickstart](https://github.com/macrunara/quickstart).

---

# AndroidExample — Macrunara Android CI 示例

最小 Android 应用（单 Activity、Java、零依赖），演示在 **Macrunara**（M4 Mac mini Apple Silicon runner）上跑 GitHub Actions CI。

fork 后立即可跑：节点镜像已预装 JDK 17（temurin）+ Android SDK（API 35、build-tools 35.0.0、NDK 27）且许可证已接受——无需任何设置步骤和 secrets。

## 使用方式

1. 从 GitHub Marketplace 把 **Macrunara** App 安装到你的组织。
2. Fork 本仓库（或把 `.github/workflows/android-gradle.yml` 复制到你自己的仓库）。
3. Push 到 `main`——job 会自动在 Macrunara M4 节点上运行，并把 debug APK 作为产物上传。

workflow 使用标准三标签 `runs-on: [macos, arm64, macrunara]`。**不要**写 `self-hosted` 或 `macos-latest`——job 会永远排队且不报错。

## 自定义

- 换构建任务：`:app:assembleRelease` 出 release APK，`:app:bundleRelease` 出 AAB。
- 加单元测试：`./gradlew testDebugUnitTest --no-daemon`。
- 更多模板（iOS / Flutter / React Native）：[macrunara/quickstart](https://github.com/macrunara/quickstart)。

---

# AndroidExample — Macrunara Android CI のサンプル

最小構成の Android アプリ（シングル Activity、Java、依存なし）で、**Macrunara**（M4 Mac mini Apple Silicon runner）による GitHub Actions CI を体験できます。

フォークですぐに実行可能：ノードイメージには JDK 17（temurin）+ Android SDK（API 35、build-tools 35.0.0、NDK 27）がプリインストールされ、ライセンスも承認済み——セットアップステップも secrets も不要です。

## 使い方

1. GitHub Marketplace から **Macrunara** App を組織にインストールします。
2. このリポジトリをフォーク（または `.github/workflows/android-gradle.yml` を自分のリポジトリにコピー）します。
3. `main` に push すると、ジョブは Macrunara M4 ノード上で自動実行され、debug APK がアーティファクトとしてアップロードされます。

ワークフローは標準の3ラベル `runs-on: [macos, arm64, macrunara]` を使用します。`self-hosted` や `macos-latest` は使用しないでください——ジョブが永遠にキューイングされたままエラーも出ません。

## カスタマイズ

- タスクの変更：`:app:assembleRelease`（release APK）、`:app:bundleRelease`（AAB）。
- ユニットテストの追加：`./gradlew testDebugUnitTest --no-daemon`。
- その他のテンプレート（iOS / Flutter / React Native）：[macrunara/quickstart](https://github.com/macrunara/quickstart)。
