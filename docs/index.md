# YMM4 API Documentation

## YMM4のプラグインシステムについて

YMM4はバージョンv4.20.0.0より本格的なプラグインの対応が始まりました。[^1]現在はさらにいくつかの種類のプラグインを製作可能となった上、個々のプラグインをとってみても多くの機能が追加されました。このドキュメントでは、プラグインの作り方、およびYMM4から提供されているAPIについて解説します。

### プラグインが継承するインターフェース、付与する属性

プラグインの名前やパラメータなどを提供するクラスは、その機能に応じて適当なインターフェースを継承したり、属性を与えたりする必要があります。ユーザーの操作やYMM4からの要求に応じて処理をするためのクラスやパラメータを保持するためのクラスは別のインターフェースや属性が必要になります。ここではそれら以外の例を示します：

| クラスの目的  | インターフェース                 | 属性            |
| :------ | :----------------------- | :------------ |
| 映像エフェクト | `VideoEffectBase`        | `VideoEffect` |
| 音声エフェクト | `AudioEffectBase`        | `AudioEffect` |
| 図形      | `IShapePlugin`           | （なし）          |
| 立ち絵     | `ITachiePlugin`          | （なし）          |
| 波形      | `IAudioSpectrumPlugin`   | （なし）          |
| 場面切り替え  | `ITransitionPlugin`      | （なし）          |
| 画像読み込み  | `IImageFileSourcePlugin` | （なし）          |
| 動画読み込み  | `IVideoFileSource`       | （なし）          |
| 音声読み込み  | `IAudioFileSourcePlugin` | （なし）          |
| 動画出力    | `IVideoFileWriterPlugin` | （なし）          |
| 音声合成    | `IVoicePlugin`           | （なし）          |
| テキスト補完  | `ITextCompletionPlugin`  | （なし）          |
| 多言語化    | `ILocalizePlugin`        | （なし）          |

### プラグインを作成する際に必要なもの

基本的に無からものを生むことは不可能です。これはコンピュータープログラムをとってみても同様に言えます。YMM4のプラグインを作成する際に必要なものは次の通りです：

- PC（Windowsが好ましい[^2]）
- Visual Studio、Visual Studio Code、Rider、Vimなどのコードエディター
- .Net 9 SDK（ビルドに必要、Visual Studioではワークロードからインストール可能）
- YMM4（プラグインにはYMM4のアセンブリが必須であるため。[上記](#_1)参照）

また、作成したプラグインを公開する際は次のような手段が必要です：

- GitHub
- BOOTH
- Google Drive
- OneDrive

なお、プラグインの作成、公開のプロセスは、別のページ（未作成）で説明します。

[^1]: この[饅頭遣いのおもちゃ箱のページ](https://manjubox.net/ymm4/release/4.20.0.0/)を参照

[^2]: YMM4はWindowsでのみ動作するため