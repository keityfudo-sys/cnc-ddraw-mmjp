# cnc-ddraw for MixMasterJP

[日本語](#日本語) | [English](#english)

---

## 日本語

### 概要

**cnc-ddraw for MixMasterJP** は、オープンソースのDirectDraw互換レイヤー
[cnc-ddraw](https://github.com/FunkyFr3sh/cnc-ddraw)をMixMasterJP向けに調整した非公式Forkです。

現行のWindows環境でMixMasterJPをウィンドウ表示・拡大表示しやすくすることを目的としています。

また、cnc-ddrawの設定ツールに日本語表示を追加しています。

---

### 主な変更点

- MixMasterJPで一部のGDI描画が消える問題への修正
- cnc-ddraw設定ツールの日本語表示対応
- 日本語/Englishの切り替え対応
- 日本国旗リソースの追加

---

### GDI描画修正について

MixMasterJP では、特定のUI操作後に再利用されるHDCにクリッピング領域が残り、
後続のGDI描画が正しく表示されない場合があります。
このForkでは、対象となるHDCのクリッピング領域をクリアする処理を追加しています。

---

### ダウンロード

一般ユーザー向けの最新版は、**Releases** からダウンロードできます。

**通常はこちらをダウンロードしてください：**
`cnc-ddraw-mmjp-v1.0.zip`

[最新版をダウンロード（Releases）](https://github.com/keityfudo-sys/cnc-ddraw-mmjp/releases/latest)

> ※「Source code (zip)」「Source code (tar.gz)」ではなく、
> **Assets** にある `cnc-ddraw-mmjp-v1.0.zip` をダウンロードしてください。

---

### 導入方法

Releaseの配布ZIPに含まれる以下のファイル・フォルダを、
MixMasterJP の `MixMaster.exe` があるフォルダへコピーします。

- `ddraw.dll`
- `ddraw.ini`
- `cnc-ddraw config.exe`
- `Shaders`フォルダ

※MixMaster側の画面設定は **「フルスクリーン」** の状態で使用してください。
※ウィンドウ表示についてはMixMaster側ではなく、cnc-ddraw側で行います。

画面サイズなどを変更したい場合は`cnc-ddraw config.exe`を使用してください。

---

### 対応バージョン/動作確認環境

本Forkは、以下の MixMasterJPクライアントで動作確認しています。

- MixMasterJPクライアント：`ver4.00464`
- 動作確認：2026年10月

`ver4.00464` は、今回実際に動作確認した MixMasterJPクライアントのバージョンです。

今後の MixMasterJPのアップデートによって描画処理やクライアント仕様が変更された場合、
本Forkが正常に動作しなくなる可能性があります。

---

### 今後の公開・配布について

本Forkは、現在のMixMasterJPにおける表示・ウィンドウ利用上の問題を補うことを目的としています。

今後、MixMasterJP公式クライアントがデュアルディスプレイ環境へ正式に対応し、
ウィンドウサイズ・表示サイズの調整など、本Forkを必要としない同等の機能が公式に提供された場合は、
本Forkの更新・配布を終了、またはリポジトリをアーカイブする可能性があります。

公式機能で同等の環境が実現できる場合は、公式クライアントの機能を優先してください。

---

### ソースコード

このリポジトリは
[FunkyFr3sh/cnc-ddraw](https://github.com/FunkyFr3sh/cnc-ddraw)
からForkしています。

MixMasterJP向けの変更はGitのコミット履歴から確認できます。

主な変更箇所：

- `src/ddsurface.c` — GDIクリッピング問題の修正
- `config/ConfigFormUnit.cpp` — 日本語表示・言語切り替え
- `config/cnc-ddraw config.cbproj` — 日本国旗リソースの登録
- `config/cnc-ddraw config_resources.rc` — 日本国旗リソースの追加
- `config/Resources/JP.PNG` — 日本国旗画像

---

### 注意事項

このプロジェクトは非公式です。

MixMasterJPの運営会社およびcnc-ddraw本家によって、
MixMasterJP向けとして公式に提供・サポートされているものではありません。

使用によって発生した問題について、MixMasterJP運営およびcnc-ddraw本家への問い合わせは行わないでください。

利用する場合は、各サービスの利用規約等を確認してください。

### Upstream

Original project: **FunkyFr3sh / cnc-ddraw**

https://github.com/FunkyFr3sh/cnc-ddraw

### License

cnc-ddraw is licensed under the **MIT License**.

詳細は、このリポジトリの `LICENSE` をご確認ください。

---

## English

### About

**cnc-ddraw for MixMaster JP** is an unofficial fork of
[cnc-ddraw](https://github.com/FunkyFr3sh/cnc-ddraw), adjusted for MixMaster JP.

This fork adds a fix for a GDI clipping issue observed in MixMaster JP and adds
Japanese language support to the cnc-ddraw configuration tool.

### Changes

- Fix for GDI drawing disappearing after certain UI interactions in MixMaster JP
- Japanese translation for the cnc-ddraw configuration tool
- Japanese / English language switching
- Japanese flag resource

### Downloads

Prebuilt packages for users will be available from **Releases**.

If no release is currently available, the package is still being prepared.

### Compatibility

This fork has been tested with:

- MixMaster JP client: `ver4.00464`
- Tested: October 2026

Compatibility with future MixMaster JP client versions is not guaranteed.
Changes to the game's rendering behavior or client implementation may affect this fork.

### Future development and distribution

This fork is intended to address display and windowing limitations currently observed in MixMaster JP.

If the official MixMaster JP client adds official multi-display support and equivalent
window/display-size adjustment features, development or distribution of this fork may
be discontinued, or this repository may be archived.

When equivalent functionality is available in the official client, the official
functionality should be preferred.

### Upstream

Original project: **FunkyFr3sh / cnc-ddraw**

https://github.com/FunkyFr3sh/cnc-ddraw

### License

cnc-ddraw is licensed under the **MIT License**.

See `LICENSE` for details.
