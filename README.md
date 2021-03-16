# dvorakjp-romantable
Google 日本語入力のデフォルトローマ字テーブルをベースに、[DvorakJP](http://www7.plala.or.jp/dvorakjp/)のマッピングを行ったローマ字テーブルです。
DvorakJP([v1.0正式版](http://www7.plala.or.jp/dvorakjp/kaitei.htm))のローマ字テーブルとしてご利用ください。


## How to use

1. [dvorakjp-romantable/dvorakjp_prime.txt](https://github.com/shinespark/dvorakjp-romantable/blob/master/dvorakjp_prime.txt) をローカルにダウンロードします。
1. Google 日本語入力のPreferences > General > Romaji table > Customize... ボタンをクリックします。
1. EditボタンからImport from file... を クリックし、dvorakjp_prime.txtを取り込み、OKをクリックします。

通常は上記手順で適用されますが、正常に適用されない場合はGoogle 日本語入力を再起動してください。

## Note

### Google 日本語入力のデフォルトローマ字テーブル

一般的なローマ字テーブルに、以下の変更が加えてありました(2015-10-11現在)。

1. `z*`キーによる矢印記号入力サポート
	- `zh`: `←`, `zj`: `↓`などの記号入力をサポート
1. 訓令式以外のローマ字入力サポート
	- `f*`, `ch*`, `ts*`など、一般的なローマ字テーブルにも存在するヘボン式ローマ字入力
	- `twa`: `とぁ`などの`w`拗音の追加
1. `t'u`: `とぅ`などの`'`を利用した拗音入力サポート
	- ただし、`twu`: `とぅ`など他の入力でも代替可能かつ、ノーヒント

Google 日本語入力のデフォルトローマ字テーブル: [romantable_original.txt](https://github.com/shinespark/dvorak-romantable/blob/master/lib/romantable_original.txt)

### DvorakJP(v1.0正式版)のローマ字テーブル

[DvorakJP - 日本語入力用拡張Dvorak](http://www7.plala.or.jp/dvorakjp/dvorakjp.htm) にて公開されているローマ字テーブルです。
左手ホームポジションに母音がすべて揃っているDvorak配列に、より日本語入力でも打鍵しやすいよう以下の拡張が行われています。

1. か行を右手側の`c*`でも入力可能
	- 多様する子音をほぼ右手のみで入力可能に
1. 拗音入力時に利用する`y`キーの代わりに、`h`, または`n`キーが入力可能
	- 多様する子音をほぼ右手のみで入力可能に
1. 二重母音拡張と撥音拡張を追加
	- 連続する母音入力(左手での連続打鍵回数)を低減

### DvorakJP Prime(dvorakjp_prime.txt)

Google 日本語入力にDvorakJPのローマ字テーブルをマージするに辺り、以下の変更を行ったローマ字テーブルです。  
このリポジトリで公開しているメインのローマ字テーブルになります。

1. Google 日本語入力の `z*`キーによる記号の入力を、`;*`に変更
	- ざ行の入力と競合する為、Qwerty時の`z`キーに位置する`;`に置換
1. Google 日本語入力の `t'u`: `とぅ`などの`'`を利用した拗音入力の削除
	- `twu`: `とぅ`などで代替入力可能な上、DvorakJPの二重母音拡張と重複する為
1. Google 日本語入力の `ch*`, `tw*` などの拗音にもDvorakJPの二重母音拡張を追加
	- `ch;neru`: `チャンネル`, `ch'ro`: `ちゃいろ` など、拗音に対しても二重母音拡張の入力が可能
	- `t*` は元々の拗音バリエーションが多いことに留意
		- `tya`: `ちゃ`, `tha`: `てゃ`, `tsa`: `つぁ`, `twa`:`とぁ`, `tna`: `ちゃ`, etc.
1. DvorakJPの`k`によるか行の二重母音拡張と拗音拡張の有効可
	- [DvorakJP](http://www7.plala.or.jp/dvorakjp/)  ではか行の入力を`c`だけに限定しているようですが、`k`でも入力可能にし、コンビネーションキーを利用した二重母音拡張と拗音拡張が利用可能
1. DvorakJP 0.2β時の`p`キーに二重母音拡張`uu`を復活
	- Google 日本語入力では連続同文字打鍵での「っ」が入れられない問題は発生しない
	- 参照: [DvorakJP - 前バージョンからの改定について](http://www7.plala.or.jp/dvorakjp/kaitei.htm)

### DvorakJP Prime with Emoji(dvorakjp_prime_with_emoji.txt)

dvorakjp_prime.txt に、絵文字変換を追加したローマ字テーブルです。  
全角で `:tada` と入力を試みると、 `🎉` に変換されます。

通常は後ろの `:` 無しでも入力可能ですが、別の emoji 名の入力途中とも判断できる emoji の入力には後ろの `:` が必要です。

```
:baseball	⚾	# baseball に続く他のemojiが存在しない為、: 無しでも確定可能
:basketball:	🏀	# basketball に続く他のemojiがある為、確定の為に : が必要
:basketball_player	⛹
```

[emojione/emojione](https://github.com/emojione/emojione/) の emoji.json を取り込んで生成しています。

#### Thanks:

* [IME でも :muscle: みたいに Emoji を入力したい！ - pockestrap](http://pocke.hatenablog.com/entry/2017/03/05/193553)
* [Add emojis · tock203/dvorakjp-romantable@341d34f](https://github.com/tock203/dvorakjp-romantable/commit/341d34fff084e945ac5a098ac14f7c48f55983e1)

## License
dvorakjp-romantable is released under the MIT License.
