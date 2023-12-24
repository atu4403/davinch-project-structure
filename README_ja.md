# Davinch Project Structure

## 概要

このリポジトリでは **DaVinci Resolve** での素材管理を一元化するためのディレクトリ構造を提案し、そのディレクトリを作成するためのシェルスクリプトを提供します。これにより、プロジェクトの整理と効率的な作業フローが実現できます。

## コマンドのインストール方法と注意点

リポジトリをクローンし、`bin`ディレクトリにパスを設定することで、以下のコマンドが使用可能になります。セキュリティと依存関係の確認を行い、適切な環境での使用をお勧めします。

```bash
git clone https://github.com/atu4403/davinch-project-structure.git
cd davinch-project-structure
export PATH=$(pwd)/bin:$PATH
```

この設定は一時的なものです。永続してコマンドを使用する場合はshellの設定ファイル(`.bashrc`や`.zshrc`など)に保存してください。

## コマンド

- `init_davinch_project`: Davinchワークスペースを初期化し、共有素材ディレクトリ（SharedMaterials）とプロジェクトディレクトリ（Projects）を作成します。
- `new_davinch_project`: 新しいプロジェクトを作成し、必要なディレクトリ構造を`Projects`内に生成します。

### `init_davinch_project`

このコマンドは、Davinchプロジェクト用の初期環境を設定します。メインディレクトリ（デフォルトでは'Davinch'、またはユーザーによって指定されたカスタム名）を作成し、共有リソースとプロジェクトスペースを整理します。

#### 作成される構造

- `Davinch/`（またはカスタム名）: 全てのプロジェクト関連資料を含むメインディレクトリ。
  - `SharedMaterials/`: 複数のプロジェクトで共通して使用されるアセットを収納するディレクトリ。
    - `Music/`: 音楽ファイルを収納し、サブカテゴリに分けられています。
      - `Favorites/`
      - `RoyaltyFreeMusic/`
      - `PaidMusic/`
    - `SoundEffects/`: 様々な効果音を収納。
      - `Favorites/`
      - `NaturalSounds/`
      - `SyntheticSounds/`
      - `UniqueSoundEffects/`
    - `Image/`: 写真、イラスト、背景画像などの画像ファイルを収納。
      - `Favorites/`
      - `Photographs/`
      - `Illustrations/`
      - `BackgroundImages/`
    - `Video/`: ビデオクリップやストックビデオを収納。
      - `Favorites/`
      - `FreeStockVideos/`
      - `PaidStockVideos/`
    - `VideoEffects/`: トランジションやフィルターなどのビデオエフェクトを収納。
      - `Favorites/`
      - `Transitions/`
      - `Filters/`
      - `Templates/`
  - `Projects/`: 個々のプロジェクトフォルダ用のディレクトリ。

### `new_davinch_project`

Davinchワークスペースの`Projects/`ディレクトリ内に新しい個別のプロジェクトを作成するために使用されます。各プロジェクトフォルダには、プロジェクト固有の資料用の整理されたサブディレクトリが含まれます。

#### 各プロジェクトのために作成される構造

- `ProjectName/`: 特定のプロジェクト用のメインフォルダで、以下の構造を含みます：
  - `RawMaterials/`: プロジェクト固有の全ての生ファイルやアセットを含む。
    - `Video/`: 主要および補足のビデオ映像を収納。
      - `MainFootage/`
      - `SupplementaryFootage/`
    - `Audio/`: ナレーションや現場での録音などのオーディオファイルを収納。
      - `Narration/`
      - `OnSiteAudio/`
    - `Image/`: プロジェクト固有の画像やKeynoteで作成されたスライドを

収納。
      - `ProjectSpecificImages/`
      - `KeynoteSlides/`
  - `Exports/`: プロジェクトの全てのエクスポート版が保存される場所。
    - 例：`Draft_YYYY-MM-DD.mp4`、`PreRelease_YYYY-MM-DD.mp4`、`Final_YYYY-MM-DD.mp4`
  - `SupportingMaterials/`: ストーリーボード、ショットリスト、台本などの追加のサポートドキュメントを含む。
    - `Storyboard.pdf`
    - `ShotList.xlsx`
    - `Script.md`

## 使用方法

- 初期Davinchワークスペースと共有リソースを作成するために`init_davinch_project`を実行します。
- `Projects/`ディレクトリ内に新しいプロジェクトを特定の構造で作成するために、`new_davinch_project [ProjectName]`を使用します。

