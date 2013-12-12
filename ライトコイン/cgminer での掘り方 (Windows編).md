---
"title": "萌えプールでcgminerを使ってライトコインを掘りましょう (Windows編)",
"tags": ["litecoin", "windows"],
"author": "Johnathan David Froeming"
---

cgminer での掘り方 (Windows編)
==============================

`LiteCoin`を掘るには、少し使い方が難しいツールを使う必要があります。
ここではいったん、`AMDのATI Radeon系`のグラフィックカードを使われているかた向けの説明を書いていきます。

### 概要
今回は`AMDのATI Radeon系`のグラフィックボートを使って説明致しますので
[cgminer](https://github.com/ckolivas/cgminer) を使います。

ちなみに、`NVIDIAのGeForce系`を使っている人は [cudaminer](https://github.com/cbuchner1/CudaMiner)を使います。

#### cgminerのダウンロードの前に

現在 `cgminer` の最新版は3.8系なのですが、残念ながら`LiteCoin`を掘ることができませんので3.7系以下のを使わないといけません。

今回は、3.7系で説明をしようと思いましたが、[hikipuro](http://bitcoin.hateblo.jp/entry/2013/12/08/144922)の情報によりますと

3.7系は、無害のマルウェアが含まれており、ウイルスチェッカーにもひっかかってしまいますのでもう一個バージョンを下げて、今回は3.6系で説明を進めますが

3.7系をダウンロードしたい人は、そのまま3.7系をダウンロードしても問題ないです。

#### いよいよ、cgminerのダウンロード。

[http://ck.kolivas.org/apps/cgminer/](http://ck.kolivas.org/apps/cgminer/) から

3.6系の最新のバージョンをダウンロードして下さい。

> 現在（2013年12月11日）は [cgminer-3.6.6-windows.zip](http://ck.kolivas.org/apps/cgminer/3.6/cgminer-3.6.6-windows.zip) が最新です。

ダウンロードが終わりましたら、好きなフォルダーに解凍して下さい。

#### cgminer.exeの実行方法

解凍したフォルダーに `cgminer.exe` が入っていると思います。

これを実行するには、いくつかのコマンドオプションを指定する必要がありますので、それを簡単にする為に

batファイルを作りたいと思います。

テキストエディタで、cgminer.bat って新規ファイルを作って下さい。

cgminer.bat内に以下の処理を書いて下さい。

```bat
setx GPU_MAX_ALLOC_PERCENT 100
setx GPU_USE_SYNC_OBJECTS 1
cgminer --scrypt -o stratum+tcp://www.moepool.com:3333 -u [ログインid.ワーカー名] -p [ワーカーパスワード]
pause
```


> `ログインid` : 萌えプールのログインid
> `ワーカー名` : 萌えプールで作成したワーカーの名前
> `ワーカーパスワード` : 萌えプールでワーカーを作った時に指定したパスワード




