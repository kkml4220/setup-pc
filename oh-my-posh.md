# how to install oh-my-posh

`oh-my-posh`のインストール方法

[oh-my-posh](https://ohmyposh.dev/)

## oh-my-posh のインストール

`Admin`権限で PowerShell で以下を実行

```PowerShell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

## Font のインストール

[oh-my-posh fonts](https://ohmyposh.dev/docs/installation/fonts)

`Admin`権限で PowerShell で以下を実行

```PowerShell
oh-my-posh font install
```

方向キーで`Hack`をインストール

## Terminal Icons をインストール

[Terminal-Icons](https://github.com/devblackops/Terminal-Icons)

`Admin`権限で PowerShell で以下を実行

```PowerShell
Install-Module -Name Terminal-Icons -Repository PSGallery
```

## Windows Terminal の設定

設定から`JSONファイルを選択`をクリック

- `Git bash`などのよく使うターミナルの表示位置やデフォルトターミナルを変更

## Prompt の変更

1. `$PROFILE`ファイルを作成

   ```PowerShell
   New-Item -Path $PROFILE -Type File -Force
   notepad $PROFILE
   ```

2. `$PROFILE`ファイルに次を追記

   ```PowerShell
   oh-my-posh init pwsh | Invoke-Expression
   ```

3. フォントを変更

   Windows terminal からフォントを`Hack Nerd Font`に変更します。

## Theme の設定

[theme](https://ohmyposh.dev/docs/themes)

1. Theme のカタログを見る

   ```PowerShell
   Get-PoshThemes
   ```

2. ローカルの Theme ファイルへのパスを通す

   デフォルトでは`Theme`は次のパスにインストールされる

   ```bash
   C:\Users\kkml4\AppData\Local\Programs\oh-my-posh\themes
   ```

   好きな`Theme`のインストールされた`json`ファイルを`$PROFILE`にコピーして次のコマンド部分にパスを指定する

   ```PowerShell
   oh-my-posh init pwsh --config "C:\Users\kkml4\Documents\WindowsPowerShell\montys.omp.json" | Invoke-Expression
   ```

## Terminal-icons を設定する

[Terminal-icons](https://github.com/devblackops/Terminal-Icons)

`C:\Users\kkml4\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`に次を追記

```
Import-Module -Name Terminal-Icons
```

## Windows Git Bash の設定

`Theme`を`Users`の直下に配置して次のコマンドを実行

```bash
eval "$(oh-my-posh init bash --config ~/montys.omp.json)"
```

きちんと`Theme`が切り替わるか確認後

次のコマンドを`~/.bashrc`に追記

```bash
eval "$(oh-my-posh init bash --config ~/montys.omp.json)"
```

再読み込み orTerminal の再起動

```bash
source ~/.bashrc
```
