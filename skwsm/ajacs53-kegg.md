# AJACS御茶ノ水　パスウェイデータベース　KEGG/GenomeNetのWebサービスの紹介

情報・システム研究機構  
ライフサイエンス統合データベースセンター  
[川島 秀一] kwsm@dbcls.rois.ac.jp  
2015年5月21日 AJACS御茶ノ水@東京医科歯科大学


----

これは統合データベース講習会 御茶ノ水「DDBJ Pipelineを用いたDNA多型注釈解析の実習」の資料です。<br>
講習会全体のプログラムは[こちら](http://events.biosciencedbc.jp/training/ajacs53)です。  

----

## 概要



##### 講習に際しての注意とお願い

- みんなで同時にアクセスするとサイトにつながりにくくなることが予想されます。
    - サイトの反応が悪い時はタイミングをずらして実行してみてください。
    - 反応が無いからと言って何度もクリックするとますます繋がらなくなってしまいます。おおらかな気持ちで臨みましょう。
- わからないことがあったら挙手にてスタッフにお知らせください。
    - 遠慮は無用です(そのための講習会です!)。おいてけぼりは楽しくありません。


##### 参考資料

- [「KEGG/GenomeNetのWebサービスの紹介」(2014年12月AJACS51岩手)](http://motdb.dbcls.jp/?plugin=attach&pcmd=open&file=KEGG_2014_12_slide.pdf&refer=AJACS51) 
- [「KEGG/GenomeNetの利用法」(2013年11月6日)](http://motdb.dbcls.jp/?plugin=attach&pcmd=open&file=KEGG_2013_11.pdf&refer=AJACS51) 

### GenomeNet 概要

- ゲノム情報を基盤とした生命科学研究を促進するためのインターネットサービス
- KEGGを中心とするデータベース群と、それらデータを解析するための計算ツール群からなっている
 - [GenomeNet Home](http://www.genome.jp/)


### bget/bfind

- bget: GenomeNetのデータベースエントリーID検索
- bfind: GenomeNetのデータベースに対するキーワード検索

####【実習1】bget/bfind検索を体験する

1. [GenomeNet Home](http://www.genome.jp/)へアクセスする。
[![GenomeNet Home](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_GenomeNet_Home.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_GenomeNet_Home.png)
2. ページ上部のテキスト検索ボックスに、好きなキーワードを入れて検索してみる。DB名:エントリーID という形式で入力するとbgetモード（例 eco:b0002）、それ以外では、bfindモードで検索が行われる。


----

### LinkDB

[![LinkDB Home](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_Home.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_Home.png)

####【実習2】LinkDBを用いて、データベースIDの変換を行う。

1. [LinkDB Home](http://www.genome.jp/linkdb/) へアクセスする。
2. データベースリンクダイアグラム中の各データベースを表す矩形をクリックし、どのようにデータベース間がリンクされているか調べてみる。（このダイアグラムでは、KEGG内データベースから外部のデータベースか、外部データベース間のリンクのみ表示される）。
[![LinkDB Link Diagram Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_diagram1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_diagram1.png)
3. ヒト遺伝子に関して、NCBI GENE と KEGG GENE の間の対応表を作成しダウンロードする。下図のように、from には、has （has は、Hono sapiens を意味する KEGGの生物種コード）を、to には、NCBI-GENE を入力し、downloadボタンを押す。
[![LinkDB Link Diagram Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_diagram2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_LinkDB_diagram2.png)
4. ダウンロードされたテキストファイルの内容を確認する。

----

### KEGG 概要

- ゲノムや分子レベルの情報から細胞、個体、エコシステムといった生命システムレベルの機能を整理したデータベース
- 遺伝子や化合物などの分子部品のデータベースと、それらをつなぐネットワークのデータベースからなっている
 - [KEGG Table of Contents](http://www.genome.jp/kegg/kegg2.html)
- KEGGのパスウェイマップでは、色が様々な意味を持っている
 - [KEGG color codes](http://www.genome.jp/kegg/kegg1c.html)

[![Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_overview1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_overview1.png)


----

### KEGG Organisms / KEGG Genomes

- KEGG に含まれる生物種カタログ
- KEGG Table of Contents の KEGG Organisms をクリック
[![KEGG2 Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG2_2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG2_2.png)

[![KEGG Genomes](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_Genomes.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_Genomes.png)

----

### KEGG Genes

- 生物種毎に、遺伝子・タンパク質配列を集めたデータベース

----

### KEGG Orthology (KO)

[![KO_Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KO_Fig1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KO_Fig1.png)

----

### KEGG Pathway

[![Pathway_Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Pathway1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Pathway1.png)

[![Pathway_Fig2](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Pathway2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Pathway2.png)


#### 一般的なKEGGパスウェイ解析の流れ

1. 先にパスウェイにマップしたい遺伝子IDセットを作成（例：有意に遺伝子発現が変動した遺伝子IDセット）
2. それら遺伝子IDをKEGG GENESのIDに変換（ID変換表はLinkDBで作成可能）
3. KEGG Mapper Pathway reconstruction サービス等でパスウェイ再構築を行う

1. 先にパスウェイにマップしたい遺伝子配列セットを作成（例：新規に読んだゲノムからの遺伝子配列セット）
2. KAAS, BlastKOALA, GhostKOALA などで、K番号割り振りとパスウェイ再構築を行う

----

### KEGG Module

- Mで始まるIDで管理されている
- PATHWAYマップより小さい単位
- 複数のタンパク質から構成される、機能単位
- 生物種間での保存度合い、複合体の形成、オペロン等を考慮し、オーソロググループの組み合わせで定義されている

----

### KEGG Mapper

####[KEGG Mapper: http://www.genome.jp/kegg/mapper.html](http://www.genome.jp/kegg/mapper.html)

- Pathway, BRITE, Module などへ、指定した遺伝子、化合物等をマップするサービス一覧

####【実習3】KEGG Mapperを用いて、パスウェイ再構築を行う。

1. [KEGG Mapper - Reconstruct Pathway](http://www.kegg.jp/kegg/tool/map_pathway.html)にアクセスする。
2. 例として準備されている、genelist.txt (single organism)の内容を表示して、全てを選択し、元のページのテキストボックスにペーストする。
[![Reconstruction pathway Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway1.png)
3. Exec ボタンを押す
4. 結果を確認する
[![Reconstruction pathway list Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Result1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Result1.png)
5. 好きなパスウェイをクリックしてどのようにマップされたか確認する。
[![Reconstruction pathway example](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Map2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Map2.png)
6. 次に、例として準備されている、genelist2.txt (multipule organisms)の内容を表示して、全てを選択し、元のページのテキストボックスにペーストする。
[![Reconstruction pathway Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway2.png)
7. 結果を確認する
[![Reconstruction pathway list Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Result2.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Result2.png)
8. 好きなパスウェイをクリックしてどのようにマップされたか確認する。
[![Reconstruction pathway example](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Map1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Pathway_Map1.png)



####【実習4】KEGG Mapperを用いて、モジュール再構築を行う。

1. [KEGG Mapper - Reconstruct Module](http://www.kegg.jp/kegg/tool/map_module.html)にアクセスする。
2. 例として準備されている、genelist.txt の内容を表示して、全てを選択し、元のページのテキストボックスにペーストする。
[![Reconstruction module Fig1](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Module1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Reconstruction_Module1.png)
3. View complete modules and 1 or 2 block missing modules を選択し、Exec ボタンを押す
4. 結果を確認する

----

### KAAS (KEGG Automatic Annotation Server)

[![Fig2](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KAAS_top1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KAAS_top1.png “KAAS Home”)

- KEGG自動アノテーションサーバー [KAAS Home](http://www.genome.jp/tools/kaas/)
- 入力:
 - 大規模シークエンスによって得られた生物種のアミノ酸や塩基配列
- 出力:
 - 配列名とKOの対応表
 - PATHWAYマップ
 - BRITE階層分類

- 配列類似性が高いというだけでなく、（片方向）ベストヒットである遺伝子同士が、よりオーソログの関係にある可能性が高く、双方向ベストヒットである遺伝子がさらにオーソログの関係にある可能性が高い
 - より詳しくは、[KAAS Help](http://www.genome.jp/tools/kaas/help.html) ページを参照

[![Fig2](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KAAS_1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KAAS_1.png “KAAS概要”) 

####【実習5】KAASを用いて、自動遺伝子アノテーションを行う。


----

### BlastKOALA / GhostKOALA

[![BlastKOALA Home](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_BlastKOALA_Home.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_BlastKOALA_Home.png)

- KOALAは、KEGG内部で、アミノ酸配列にK番号を割り当てるために利用しているシステム。
- BlastKOALA および GhostKOALAは、ユーザの入力配列に対して、BLAST または GHOSTX を利用して、K番号を割り当てるシステム
 - KAAS の single-best に近い
 - 検索対象の配列データベースを絞っているため、KAASより高速にK番号の割り当てが行える。GHOSTX の方が BLASTより高速なため、BlastKOALA より GhostKOALAの方がさらに高速である。

####【実習6】BlastKOALAを用いた、自動遺伝子アノテーション／パスウェイ再構築を行う。


1. [KEGG Mapper - Annotate Sequence by BlastKOALA](http://www.kegg.jp/kegg/tool/annotate_sequence.html) にアクセスする
![KEGG Mapper - Annotate Sequence by BlastKOALA](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_Mapper_Sequence_Annotation_Home.png)
2. Example として準備されている、sequence.txt をダウンロードし、Choose File ボタンをクリックして選択する（もしくは、sequence.txt を別途ブラウザ上で表示し、コピーしたのち、Enter FASTA Sequence テキストボックスへペーストする）
3. Select GENES family/genus dataset to be searched メニューで、Select Family/Genus ボタンをクリックする。別ウィンドウとして、Family/Genus を選択するページが表示されるので、Buchnera を見つけてクリックする
4. 元のページに戻るので、Exec ボタンを押す
5. しばらく待つと、以下のような結果ページが表示される
[![SequenceAnnotationResult](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Sequence_Annotation_Result1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_Sequence_Annotation_Result1.png)
6. Pathway, Module, BRITE などがどのように再構築されたか確認する

----



