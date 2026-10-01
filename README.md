# rustysynth-test

SoundFont と MIDI ファイルを読み込み、音楽を再生しながら波形を表示します。

## ビルドと実行

Rust 1.86 以降、CMake、C++ ビルドツールが必要です。Windows では Visual Studio の「C++ によるデスクトップ開発」を使用します。

```powershell
cargo build
cargo run -- soundfont.sf2 song.mid
```

SoundFont と MIDI ファイルは別途用意してください。

Windows で `Could not create named generator Visual Studio 18 2026` が出る場合、PATH 上の CMake が古いため、Visual Studio 付属の CMake に切り替えます。同じ PowerShell セッションで以下を実行してください。

```powershell
$vsInstall = & "${env:ProgramFiles(x86)}\Microsoft Visual Studio\Installer\vswhere.exe" -latest -products '*' -requires Microsoft.VisualStudio.Component.VC.Tools.x86.x64 -property installationPath
$env:PATH = "$vsInstall\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin;$env:PATH"
cargo build
```
