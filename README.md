# Windows Yuzu導入方法 (Switch Firmware17.00以降)
# yuzu-mainlineは削除されました
代わりにsuyuが使えます
また、yuzuも[一部サイト](https://tas.monsterdruide.one/yuzu/)で入手することができます
# 前提条件
CFW導入済みのSwitch

# ダウンロード
① [Visual C++](https://learn.microsoft.com/ja-JP/cpp/windows/latest-supported-vc-redist?view=msvc-170#:~:text=https%3A//aka.ms/vs/17/release/vc_redist.x64.exe)

② [Yuzu emulator](https://yuzu-emu.org/downloads/)

③ [nxdumptool](https://github.com/DarkMatterCore/nxdumptool/releases/tag/rewrite-prerelease)

④ [Lockpick_RCM](https://vps.suchmeme.nl/git/mudkip/Lockpick_RCM/releases)

⑤ [TegraExplorer](https://github.com/suchmememanyskill/TegraExplorer/releases/latest)


# title.keys prod.keys
1 Lockpick_RCM.binをTegraRcmGUIでペイロード

2 虹色の画面が出てきたら`Dump keys from SysNAND`を選択し、電源ボタン(決定)を押す

3 音量ボタンを押して次の画面に移行したら、`power off`を選択(音量ボタンでカーソル移動)し、電源ボタンを押す

# TegraExplorer
1 TegraExplorer.binをTegraRcmGUIでペイロード

2 `FirmwareDump.te`→`Dump sysmmc` 電源ボタンでdump開始

3 dump完了後、何かしらのキーを押して`Reboot to RCM`

# nsp
1 hbmenuからnxdt_rw_pocを選択

2 `user titles menu`→ダウンロードしたいゲームのid→`nsp dump options→dump base application`

3 `tik: remove sconsole specific data`が`no`になっていれば`yes`を選択

4 start nsp dumpを開始　`以降hbmenuに戻るまでホームボタンを厳禁`

5 抽出完了後、+ボタンでhbmenuへ戻る

6 適当な場所にnspファイルを保存

# yuzu
1 yuzu.exeを起動

2 keyが無いと言われるのでokをクリック

3 `Emulation > Configure... > General > UI > General > Interface language` `Japanese`に変更

4 ファイル>yuzuフォルダーを開く　`C:\～\yuzu\keys`にLockpick_RCMでdumpした`title.keys prod.keys`を貼り付け

5 yuzu.exeを再起動

6 `新しいゲームディレクトリを追加する` 保存したnspファイルの場所を選択

# ファームウェアのインストール 
1 ファイル>yuzuフォルダーを開く　`C:\～\yuzu\nand\system\Contents\registered`

2 TegraExplorerでdumpしたncaファイルをすべて貼り付け

# NvidiaGPU最適化
1 [最新ドライバー](https://www.nvidia.co.jp/Download/index.aspx?lang=jp)をダウンロード

2 `NVIDIAコントロールパネル > 3D設定の管理 > プログラム設定` `C:\～\yuzu.exe`を選択

```
スレッドした最適化　　　　　　　　　　　　  　　    オン
```
```
テクスチャ フィルタリング-クオリティー　　  　　  　クオリティー
```
```
テクスチャ フィルタリング-トリリニア最適化  　　    オン
```
```
テクスチャ フィルタリング-ネガティブLODバイアス     許可
```
```
テクスチャ フィルタリング-異方向サンプル最適化      オフ
```
```
トリプル バッファリング　　　　　　　　　　　　   　オフ
```
```
低遅延モード　　　　　　　　　　　　　　　　　　　  ウルトラ
```
```
垂直同期　　　　　　　　　　　　　　　　　　　　　  高速
```
```
電源管理モード　　　　　　　　　　　　　　　　　　  パフォーマンス最大化を優先
```

