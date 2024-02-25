# Windows Yuzu導入方法 (Switch Firmware17.00以降)
# 前提条件
CFW導入済みのSwitch
# ダウンロード
① [Visual C++](https://learn.microsoft.com/ja-JP/cpp/windows/latest-supported-vc-redist?view=msvc-170#:~:text=https%3A//aka.ms/vs/17/release/vc_redist.x64.exe)
② [Yuzu emulator](https://yuzu-emu.org/downloads/)
③ [nxdumptool](https://github.com/DarkMatterCore/nxdumptool/releases/tag/rewrite-prerelease)
④ [Lockpick_RCM](https://vps.suchmeme.nl/git/mudkip/Lockpick_RCM/releases)

#手順
1 SDカードのSwitchフォルダーに③のnroファイルを入れる
2 ④のbinファイルをTegraRcmGUIでペイロード
3 虹色の画面が出てきたらDump keys from SysNANDを選択し、電源ボタン(決定)を押す
4 音量ボタンを押して次の画面に移行したら、power offを選択(音量ボタンでカーソル移動)し、電源ボタンを押す
5 ペイロードするファイルを変更し、いつも通りCFWを起動
6 hbmenuからnxdt_rw_pocを選択
7 user titles menu→ダウンロードしたいゲーム→nsp dump options→dump base application
8 `tik: remove sconsole specific data`が`no`になっていれば`yes`を選択
9 start nsp dumpを開始　`以降hbmenuに戻るまでホームボタンを厳禁`



