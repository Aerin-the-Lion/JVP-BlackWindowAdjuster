# JVP-BlackWindowAdjuster
JavPlayer has the critical bug that created video would be lack some frames by it. It will fix this.

まだ作ってません。<br>
とりあえず参考になりそうなリンク集。

FFmpeg 動画の前後に無音黒画面を挿入<br>
https://qiita.com/takmot/items/b3d444b78bc235d37679<br>
FFMPEG で先頭と後ろを一度にカットする<br>
https://nico-lab.net/cut_before_after_with_ffmpeg/<br>
<br>
この程度のことはPowerShellで実装していけたらと思います。<br>

# なにが問題なの？
実際、何が問題かというと、JavPlayerのシークバーで前後全てを指定したはずなのに、前4フレーム、後12フレーム（？）が欠けます。
こんなのどうでも良いでしょ、と思われる方が大勢いますが、オリジナルファイルとフレーム数が違うと、その後のアップスケーリングに極めて不便となるので、修正します。

簡単にいえば、元動画の前後に黒画面を追加し、それらを代わりにに欠けさせてあとは追加した黒画面を削除させれば完璧となるわけです。
フレーム数を完璧に合わせられれば前処理だけで行けそうですが。どうでしょうか。
