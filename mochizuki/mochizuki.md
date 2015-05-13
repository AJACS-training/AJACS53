# AJACS御茶ノ水 DDBJ Pipelineを用いたDNA多型注釈解析の実習

国立遺伝学研究所 大量遺伝情報研究室  
[望月孝子](http://researchmap.jp/Takako.M/) tm@nig.ac.jp  
2015年5月20日 AJACS御茶ノ水@東京医科歯科大学


----

これは統合データベース講習会 御茶ノ水「DDBJ Pipelineを用いたDNA多型注釈解析の実習」の資料です。<br>
講習会全体のプログラムは[こちら](http://events.biosciencedbc.jp/training/ajacs53)です。  

----

## 概要

本講習は、DDBJ Read Annotation Pipeline (DDBJ Pipeline) を使用して、新型シーケンサ配列のアーカイブデータベース (DDBJ SRA) の 全ゲノム配列をリファレンスゲノムにマッピング、リファレンスゲノムとの配列比較からDNA多型の検出、そして、検出されたDNA多型に既知遺伝子アノテーションの注釈を行います。

----

## 講習の流れ<br>
今回の講習では、コンピュータを使って以下の内容について説明します。

【実習】
- DDBJ Pipeline 基礎処理部 (https://p.ddbj.nig.ac.jp/) にてDDBJ SRAの公開データのインポート、マッピング
- DDBJ Pipeline 高次処理部 p-galaxy (https://p-galaxy.ddbj.nig.ac.jp) にてDNA多型の検出、既知遺伝子注釈

----

##### 講習に際しての注意とお願い

- みんなで同時にアクセスするとサイトにつながりにくくなることが予想されます。
    - サイトの反応が悪い時はタイミングをずらして実行してみてください。
    - 反応が無いからと言って何度もクリックするとますます繋がらなくなってしまいます。おおらかな気持ちで臨みましょう。
- わからないことがあったら挙手にてスタッフにお知らせください。
    - 遠慮は無用です(そのための講習会です!)。おいてけぼりは楽しくありません。

----

##### 実習を始める前に
 
- DDBJ Read Annotation Pipeline とは
    - [DDBJ Pipeline 基礎部](https://p.ddbj.nig.ac.jp)
    - [DDBJ Pipeline 高次処理部](https://p-galaxy.ddbj.nig.ac.jp/)
    [![Gyazo](https://i.gyazo.com/37af6d0d753d3ab2430cb9a5be9e66c5.png)](http://gyazo.com/37af6d0d753d3ab2430cb9a5be9e66c5)
	
- DNApod: DNA Polymorphism AnnOtation Database とは   
    - [DNApod](http://tga.nig.ac.jp/dnapod/)
    - 本日の講習はDNApod ワークフローの講習になります。
	 [![Gyazo](https://i.gyazo.com/334f97458ccbe790417fd25cadef0c8b.png)](http://gyazo.com/334f97458ccbe790417fd25cadef0c8b)
　 

- DRAデータサーチ方法
    - [DBCLS SRA Metadata Search](http://sra.dbcls.jp/search)
    - [マニュアル](https://github.com/inutano/soylatte/blob/master/README.md)
	 [![Gyazo](https://i.gyazo.com/6eed94c401664483d46a7e8c6e0318ab.png)](http://gyazo.com/6eed94c401664483d46a7e8c6e0318ab)
  
----

####【実習】DNA多型注釈 DNApod ワークフロー 
- 本日の実習の流れ  
[![Gyazo](https://i.gyazo.com/c0da4201432980d7ac4df772d8657d91.png)](http://gyazo.com/c0da4201432980d7ac4df772d8657d91)

1. DDBJ Pipeline 基礎処理部へのアクセス
　[![Gyazo](https://i.gyazo.com/441ce21443bbd8c8b7a6e1238bd3565b.png)](http://gyazo.com/441ce21443bbd8c8b7a6e1238bd3565b)

2. DDBJ pipeline 基礎部へのログイン<br>
　講習用のID と パスワードでログインしてください。<br>　
　ご自分のデータでの解析を行う場合は、アカウントを取得してください。  
　[![Gyazo](https://i.gyazo.com/4a347a701d0c80b831364a620f116082.png)](http://gyazo.com/4a347a701d0c80b831364a620f116082)

3. クエリの選択<br>
　今回の講習用データは、DRAの公開データを使用します。<br>　　
　今回の講習で使用するERA013525のデータは既にインポート済みですが、実際にDRAのデータを解析したい場合は、データインポートを行ってください。また、ご自分のローカルPCにあるFastq fileを使用して解析したい場合は、FTP uploadの機能が使えます。<br>
　DRAのデータフォーマットの意味は、[DDBJ Sequence Read Archive Handbook](http://trace.ddbj.nig.ac.jp/dra/submission.html) をご確認下さい。 <br>
　[![Gyazo](https://i.gyazo.com/7036d30fe0cb46575089f5fd92a5273f.png)](http://gyazo.com/7036d30fe0cb46575089f5fd92a5273f)

4. マッピングツールの選択<br>
　今回はbwaを使ってマッピングしていきます。<br>
　各ツールの説明は、Tool名のリンクをクリックしてください。各Toolのwebサイトで確認することができます。
　[![Gyazo](http://i.gyazo.com/a0ad1cddb783899078deec0c3fc0e23d.png)](http://gyazo.com/a0ad1cddb783899078deec0c3fc0e23d)

5. クエリセットの作成<br>
　クエリに使用するRun accessionが複数ある場合、この機能を使用します。<br>
　今回はRun accessionが1つしかないので、あまり気にせず、セット作成を行って下さい。
　[![Gyazo](https://i.gyazo.com/9c895effcc6c40baeabbd289832b1d37.png)](http://gyazo.com/9c895effcc6c40baeabbd289832b1d37)

6. リファレンスの指定<br>
　今回の講習では、ローカルファイルをアップロードすることでリファレンスを指定する。<br>
　リファレンスFASTAファイルはこちらからダウンロードしてください。<br>
  - Escherichia coli_ O157:H7 str. Sakai (ftp://tga.nig.ac.jp/dnapod/sequence1.fasta)
  [![Gyazo](https://i.gyazo.com/f8b7141f9671f769a41f0882f854800a.png)](http://gyazo.com/f8b7141f9671f769a41f0882f854800a)

7. 実行パラメータを設定<br>
  必要に応じて実行パラメータを変更してください。<br>
  パラメータの詳細は、各ツールのHELPをご確認下さい。
 [![Gyazo](https://i.gyazo.com/82f49bc5ad01f6d1eabb5dc2275d9186.png)](http://gyazo.com/82f49bc5ad01f6d1eabb5dc2275d9186)

8. 実行条件の確認<br>
 [![Gyazo](https://i.gyazo.com/382d82ab63c5944bb1791dc74ffd39d6.png)](http://gyazo.com/382d82ab63c5944bb1791dc74ffd39d6)

9. 実行結果の確認<br>
 高次処理部にて、基礎部の実行結果をインポートする。その際に、JOBIDが必要になるので覚えておく。<br>
 今回の例のJOBIDは17855。
 [![Gyazo](https://i.gyazo.com/08a355e0594e12819d5353c5f6dd5456.png)](http://gyazo.com/08a355e0594e12819d5353c5f6dd5456)

10. 実行結果の確認　-詳細-
 [![Gyazo](https://i.gyazo.com/104efad3bf5dc1834dcce4f2ce26fc3e.png)](http://gyazo.com/104efad3bf5dc1834dcce4f2ce26fc3e)

11. 基礎処理部のログアウト
 [![Gyazo](https://i.gyazo.com/257fe530ee42a382543e43fc29443eef.png)](http://gyazo.com/257fe530ee42a382543e43fc29443eef)

12. 高次処理部 (p-galaxy) へのアクセス
 [![Gyazo](https://i.gyazo.com/22b1f42c50b89656e13630b7863ede55.png)](http://gyazo.com/22b1f42c50b89656e13630b7863ede55)

13. 高次処理部 (p-galaxy) へのログイン
　[![Gyazo](https://i.gyazo.com/e988ad50319a380c727d24f068351afa.png)](http://gyazo.com/e988ad50319a380c727d24f068351afa)

13.  ヒストリーの作成
　[![Gyazo](https://i.gyazo.com/3bec493e88e0b79e1bde46c1ba01a33e.png)](http://gyazo.com/3bec493e88e0b79e1bde46c1ba01a33e)

14. 基礎処理部のsamtools mpileupデータインポート<br>
　今回の例のJOBIDは17855。このIDの結果をインポートする。
　[![Gyazo](http://i.gyazo.com/755f1f489b922504800257c76ca9ee19.png)](http://gyazo.com/755f1f489b922504800257c76ca9ee19)
15. ホモSNPsの検出
　[![Gyazo](http://i.gyazo.com/e1a7cf108db815d2e5dcb13faa7c637e.png)](http://gyazo.com/e1a7cf108db815d2e5dcb13faa7c637e)

17. SNPsアノテーション SnpEff
　[![Gyazo](https://i.gyazo.com/204fea97753f174ddd1a04d9d68e6a76.png)](http://gyazo.com/204fea97753f174ddd1a04d9d68e6a76)

18. SNPsアノテーション SnpEff 出力ファイル (1) アノテーション情報
  [![Gyazo](https://i.gyazo.com/633d54210a50a47ee0f0916327a979c0.png)](http://gyazo.com/633d54210a50a47ee0f0916327a979c0)

19. SNPsアノテーション SnpEff 出力ファイル (2) 統計情報
  [![Gyazo](https://i.gyazo.com/a51cf957360b8e886a587be9f36117bf.png)](http://gyazo.com/a51cf957360b8e886a587be9f36117bf)

----

講習は以上です。<br>
お疲れ様でした。<br>

ご不明点があれば、pipeline_dev@ddbj.nig.ac.jp へお問い合わせください。
