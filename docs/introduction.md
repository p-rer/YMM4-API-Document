# はじめに

## プラグインが継承するインターフェース、付与する属性

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
