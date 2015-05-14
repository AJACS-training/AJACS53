
# AJACS御茶ノ水 遺伝子発現DB・ウェブツールの使い方　応用・実践編

日本大学生物資源科学部  
動物生体機構学研究室  
沖 嘉尚 oki@brs.nihon-u.ac.jp  
2015年5月21日 AJACS御茶ノ水@東京医科歯科大学 


----

## 概要

本講習は、誰でも自由に使うことができる公共データベースからマイクロアレイ解析のサンプルデータを検索し、ウェブツールを活用して発現差のある遺伝子群を抽出する方法について学びます。また、得られた数百〜数千におよぶ遺伝子群について、生物学的な解釈をする方法とその結果の考察を実践します。

----

## 講習の流れ
今回の講習では、コンピュータを使って以下の内容について説明します。

- 公共の遺伝子発現データベース NCBI Gene Expression Omnibus（GEO）の使い方
    - NCBI GEO 
        - 【実習1】GEOを使って、興味あるマイクロアレイの実験データセットを検索する
- 遺伝子発現データ解析ツール GEO2R の使い方
    - NCBI GEO2R
        - 【実習2】GEO2Rを使って、GEOに登録されているマイクロアレイデータを解析する
- 遺伝子群の機能解析ツール DAVID の使い方
    - DAVID
        - 【実習3】DAVIDを使って、発現データの解析結果を生物学的に解釈する

----

##### 講習に際しての注意とお願い

- みんなで同時にアクセスするとサイトにつながりにくくなることが予想されます。
    - 資料を見ながら自力で進められそうな方はどんどん先に、そうでない方は講師と一緒にすすめていきましょう。
    - サイトの反応が悪い時はタイミングをずらして実行してみてください。
    - 反応が無いからと言って何度もクリックするとますます繋がらなくなってしまいます。おおらかな気持ちで臨みましょう。
- わからないことがあったら挙手にてスタッフにお知らせください。
    - 遠慮は無用です(そのための講習会です!)。おいてけぼりは楽しくありません。

----

## 公共の遺伝子発現データベース NCBI Gene Expression Omnibus（GEO）の使い方
### [GEO](http://www.ncbi.nlm.nih.gov/geo/)
- NCBIが提供・維持管理している世界最大の遺伝子発現情報（マイクロアレイ）のデータベース
- [http://www.ncbi.nlm.nih.gov/geo/](http://www.ncbi.nlm.nih.gov/geo/)
- 自分の興味のある発現データセットや遺伝子プロファイルを検索することができるだけでなく、それらの生データを自由にダウンロードすることが可能です。

  - GEOのエントリについて（GEO ID番号の最初の3文字の意味）
    - GPL: Platform ー マイクロアレイチップの種類
    - GSM: Sample ー 1枚のマイクロアレイチップから得られたサンプルデータ
    - GSE: Series ー 1つの実験で得られたGSMのセット
    - GDS: DataSet ー NCBIのスタッフが解析可能なデータを集めて再編成したGSMのセット

####【実習1】GEOを使って、興味あるマイクロアレイの実験データセットを検索する
- [【復習用】NCBI GEOの使い方1〜マイクロアレイデータの検索・取得〜 2011](https://www.youtube.com/watch?v=WS5gDfG2Now)


1. 画面右側の Browse Content から「Platforms」を選択します。

 [![Gyazo](http://i.gyazo.com/d292072e90e0f09cf5ca405a37d88490.png)](http://gyazo.com/d292072e90e0f09cf5ca405a37d88490)
 
2. Platform（マイクロアレイの種類）の一覧画面が表示されるので、上部の「FIND PLATFORM」をクリックします。

 [![Gyazo](http://i.gyazo.com/218923e07e6572379e2f4b827f63b67f.png)](http://gyazo.com/218923e07e6572379e2f4b827f63b67f)
 
3. Platformの検索画面が現れるので、「Manufacturer」に "Affymetrix"、「organism」に "Homo sapiens"  を選択し、「OK」をクリックします。

 [![Gyazo](http://i.gyazo.com/7f0df6b2e1f43be6a266ba072a5ac6e4.png)](http://gyazo.com/7f0df6b2e1f43be6a266ba072a5ac6e4)

4. Affymetrixのヒトのマイクロアレイの検索結果が表示されます。列見出しをクリックすると各項目でソートできます。表の中央にある「Samples」あるいは「Series」を2回クリックすると、登録されている実験データが多い順にソートされます。

 [![Gyazo](http://i.gyazo.com/7465f25b115b92b1b9195267b12f81b4.png)](http://gyazo.com/7465f25b115b92b1b9195267b12f81b4)

5. [HG-U133_Plus_2] Affymetrix Human Genome U133 Plus 2.0 Array が最も多くデータが登録されているプラットホームであることがわかります。

6. Series数"3855"をクリックすると、Filter に "Platform: GPL570" が表示され、「Affymetrix Human Genome U133 Plus 2.0 Array」を用いた実験データのみが表示されます。

 [![Gyazo](http://i.gyazo.com/04945f061f2d38a3ba7c4954aa5a18f3.png)](http://gyazo.com/04945f061f2d38a3ba7c4954aa5a18f3)

7. 今回は 『アルコール性肝炎』 に関連するデータを検索します。検索窓に "alcoholic hepatitis" を入力して、「Search」をクリックします。

 [![Gyazo](http://i.gyazo.com/1f7f7b8dd3a7f9f6ecdd5a032c0bec0f.png)](http://gyazo.com/1f7f7b8dd3a7f9f6ecdd5a032c0bec0f)

8. GSE28619 - Transcriptome Analysis Identifies Fn14, a TNF Superfamily Receptor Member, as a Therapeutic Target in Alcoholic Hepatitis というデータセットが見つかりました。左端にある「GSE28619」をクリックすると、そのデータセットの詳細情報が閲覧できます。

 [![Gyazo](http://i.gyazo.com/7944ef43a7d9e4ec1edcbbf2de63bbb4.png)](http://gyazo.com/7944ef43a7d9e4ec1edcbbf2de63bbb4)

9. GSE28619のページが表示されました。

 [![Gyazo](http://i.gyazo.com/ccdb8f61750616ac60b0b9dac1950d75.png)](http://gyazo.com/ccdb8f61750616ac60b0b9dac1950d75)

10. ページ下部の「Download family」の中にある「Series Matrix File(s)」をクリックすると、正規化済みのデータのダウンロードリンクが表示されます。
11. ページ最下部の「Supplementary file」にあるリンクから生データをダウンロードすることができます。

 [![Gyazo](http://i.gyazo.com/4ef19d932765325d496ffaaa7b13150e.png)](http://gyazo.com/4ef19d932765325d496ffaaa7b13150e)

12. 自分の研究テーマに近い、また興味のあるマイクロアレイデータが利用可能か検索してみましょう。


----

## 遺伝子発現データ解析ツール GEO2R の使い方
### [GEO2R](http://www.ncbi.nlm.nih.gov/geo/geo2r/)
- NCBIが提供しているマイクロアレイデータの解析ツール
- [http://www.ncbi.nlm.nih.gov/geo/](http://www.ncbi.nlm.nih.gov/geo/)
- 統計解析ソフト [R](http://www.r-project.org) をベースに解析します。
- GEOに登録されているデータセットの中から、それぞれのサンプルデータを比較したいグループに分け、統計解析することによって発現量に差がある遺伝子群のリストを取得できます。

####【実習2】GEO2Rを使って、GEOに登録されているマイクロアレイデータを解析する
- [【復習用】NCBI GEOの使い方5～GEO2Rを使う～](http://togotv.dbcls.jp/20120524.html)

1. 【実習2】は、【実習1】で検索した実験データセット[GSE28619](http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE28619)の画面からスタートします。

 [![Gyazo](http://i.gyazo.com/cb03a01a98511be4c83e7ee7965b09f4.png)](http://gyazo.com/cb03a01a98511be4c83e7ee7965b09f4)

2. ページ下部の「Analyze with GEO2R」をクリックし、GEO2Rのページに移動します。

 [![Gyazo](http://i.gyazo.com/020666a58df1903d5532f62ffd9cf5f7.png)](http://gyazo.com/020666a58df1903d5532f62ffd9cf5f7)

3. データセットに含まれるサンプルデータの一覧が表示されます。列見出しをクリックすると各項目でソートできます。このデータセットには、健常者 7名・アルコール性肝炎患者 15名の肝臓から得られた22個のサンプルデータからなることがわかります。

 [![Gyazo](http://i.gyazo.com/ad82f7f81091ab7cf300fdba8819bf96.png)](http://gyazo.com/ad82f7f81091ab7cf300fdba8819bf96)

4. 比較したいグループを設定します。「Define groups」をクリックして、それぞれのグループ名を入力します。今回は、"Control" と "Alcoholic Hepatitis" をグループ名として、各サンプルをグループ化します。

 [![Gyazo](http://i.gyazo.com/c0ffdfee96f01a4f6bac24231fa35b7c.png)](http://gyazo.com/c0ffdfee96f01a4f6bac24231fa35b7c)

5. グループに入れたいサンプルをクリックやドラッグで選択してからグループ名をクリックすると、サンプルがグループに登録されます。

 [![Gyazo](http://i.gyazo.com/2b18becb49fedce34278863171cfccf6.png)](http://gyazo.com/2b18becb49fedce34278863171cfccf6)

6. 「Samples」をクリックして、サンプルデータの一覧画面を閉じます。「Value distribution」タブを選択し、「View」をクリックすると各サンプルの発現分布を調べることができます。（※ GEO2R では、投稿された生のデータを用いて解析されます。ジョブの実行は時間がかかるので要注意！）

 [![Gyazo](http://i.gyazo.com/092c364b3f1234f66fabea4c15083081.png)](http://gyazo.com/092c364b3f1234f66fabea4c15083081)

7. 発現分布が箱ひげ図で示されます。

 [![Gyazo](http://i.gyazo.com/703e9741efbda2813cb4d6db5a478ebb.png)](http://gyazo.com/703e9741efbda2813cb4d6db5a478ebb)

8. 「Export」 をクリックすると、箱ひげ図で与えられている値をまとめたタブ区切りテキストが表示されます。（※）

 [![Gyazo](http://i.gyazo.com/54d346c0f379392751bd7eaea880f947.png)](http://gyazo.com/54d346c0f379392751bd7eaea880f947)

9. GEO2R タブに戻り、「Top 250」をクリックすると、選択したグループ間で各遺伝子の発現量に差があるかどうか統計解析されます。（※）

 [![Gyazo](http://i.gyazo.com/a366350fc4069c2a5f77bf2e5c01df4a.png)](http://gyazo.com/a366350fc4069c2a5f77bf2e5c01df4a)

10. 結果が表示されました。t 検定の結果が P 値の小さい順に 250 件表示されます。

 [![Gyazo](http://gyazo.com/fddd13b327b76c5f6d20c16c905f4c97.png)](http://gyazo.com/fddd13b327b76c5f6d20c16c905f4c97)

11. "P.Value" は元の P 値、"adj.P.Val" は多重検定の補正をかけた後の P 値です。有意性の評価は adj.P.Val に基づいています。 "t" は普通の t の標準偏差を全遺伝子の標準偏差を用いて調整したもの (moderated-t) です。普通の t より精度が上がっていますが、普通の t 分布に従うものとして扱えます。 "B" は2つのグループで発現量が異なっている対数オッズ値です。exp(B)/(1+exp(B)) の値が、発現量が異なっている確率です。"logFC" は、発現量の差が何倍であるかを2底の対数にしたものです。つまり値が 2 なら 4 倍の差を示しています。ここでの解析では発現量が対数で与えられている必要がありますが、元のデータでは対数になっていないことがあります。そのような場合デフォルトでは自動検出し、対数変換して計算してくれます。その上でこのような表示がされます。

12. 各行をクリックすると、その行の遺伝子の各サンプルでの発現量のグラフが見られます。
13. 今回は健常者 vs アルコール性肝炎患者の間で最も差が大きいとされた遺伝子である AKR1B10（アルドケト還元酵素ファミリーの一つ）について見てみましょう。AKR1B10 は、健常者と比較してアルコール性肝炎患者で発現が高いことがわかります。

  [![Gyazo](http://i.gyazo.com/ae49254bb7651c7a940526255add19ce.png)](http://gyazo.com/ae49254bb7651c7a940526255add19ce)

14. また、2番目に発現差が大きいとされた遺伝子である SLC16A10（SLCトランスポーターの一つ）は、アルコール性肝炎患者で発現が低いことがわかります。

  [![Gyazo](http://i.gyazo.com/b956e24351811866ccdec210a91892b3.png)](http://gyazo.com/b956e24351811866ccdec210a91892b3)

15. 「Sample values」 をクリックすると、発現量の値が一覧できます。

 [![Gyazo](http://i.gyazo.com/cd38113a2f33785a697a77a2d89b1271.png)](http://gyazo.com/cd38113a2f33785a697a77a2d89b1271)

16. 「Select columns」 をクリックすると、表示するカラムを変更できます。 "t-statistic" と "B-value" を消し、 "GO:Process" を追加してみましょう。設定を変更したら、「Set」をクリックします。

 [![Gyazo](http://i.gyazo.com/e542c7444cf0a59190f4b4fbf155ffd7.png)](http://gyazo.com/e542c7444cf0a59190f4b4fbf155ffd7)

17. 表示するカラムを変更できました。

 [![Gyazo](http://i.gyazo.com/d92baab7929e59246bf9047cbebec466.png)](http://gyazo.com/d92baab7929e59246bf9047cbebec466)

18. 「Save all results」 をクリックすると、結果をテキストで表示・保存できます。

 [![Gyazo](http://i.gyazo.com/36519a703f95ba99c58956785a5af499.png)](http://gyazo.com/36519a703f95ba99c58956785a5af499)

19. Options タブをクリックすると、いくつかの設定を変更できます。左の項目は多重検定の補正法の選択です。デフォルトでは  "Benjamini & Hochberg" の方法が使われています。中央はデータの対数をとるかどうかの選択です。デフォルトでは自動検出で対数になります。右の項目はプラットフォームの注釈の選択です。"NCBI generated" がある場合はそれの方が信頼できます。

 [![Gyazo](http://i.gyazo.com/85b9e41924f0ad20d9e15a922a61987f.png)](http://gyazo.com/85b9e41924f0ad20d9e15a922a61987f)

20. Options に変更を加えたら、GEO2R タブに戻って 「Recalculate」 をクリックします。（※ 今回は実行しません。）

 [![Gyazo](http://i.gyazo.com/4bbc1ffff2f88145c4bf25d6f3452d3d.png)](http://gyazo.com/4bbc1ffff2f88145c4bf25d6f3452d3d)

21. Profile graph の項目では、プローブ ID を元に、個々の遺伝子の発現状況を調べることができます。Enter ID の窓にプローブ IDをコピペし、「Set」をクリックすると発現量のグラフが表示されます。今回は例として、"ALDH2"（アルデヒド脱水素酵素のアイソザイム）のプローブ ID "201425_at" を検索してみましょう。

 [![Gyazo](http://i.gyazo.com/f3cfe393c8c171668c033dc8e14ea44d.png)](http://gyazo.com/f3cfe393c8c171668c033dc8e14ea44d)

22. 健常者の方がアルコール性肝炎患者よりも ALDH2  の発現量に高い傾向がみられました。（この操作では何の計算も実行されないので、検定の結果の P 値を調べることはできません。）

 [![Gyazo](http://i.gyazo.com/541c26af2297c69cefd343972960763b.png)](http://gyazo.com/541c26af2297c69cefd343972960763b)

23. R script タブをクリックすると、これまでに実際に実行された R のスクリプトを見ることができます。これを参考に、手元の R でパラメータを調整するなどして更なる解析を行うことができます。

 [![Gyazo](http://i.gyazo.com/83c0194b675e1dab61102cea0abaf5be.png)](http://gyazo.com/83c0194b675e1dab61102cea0abaf5be)

- R の使い方については、下記の統合TV のコンテンツ「統計解析ソフト「R」の使い方」シリーズをご覧ください。
  - [統計解析ソフト「R」の使い方 ～導入編～](https://www.youtube.com/watch?v=xLZnDo9xE2g)
  - [統計解析ソフト「R」の使い方 ～ヒートマップ編～](https://www.youtube.com/watch?v=jgRboSJGK-k)
  - [統計解析ソフト「R」での立廻り](https://www.youtube.com/watch?v=QivkpL0susI)

---- 
## 遺伝子群の機能解析ツール DAVID の使い方
### [DAVID: The Database for Annotation, Visualization and Integrated Discovery](http://david.abcc.ncifcrf.gov/)
- 実験によって得られた数十～数千の遺伝子群の機能解析ツール
- [http://david.abcc.ncifcrf.gov/](http://david.abcc.ncifcrf.gov/)
- 個々の遺伝子に付与されているアノテーション情報（GO term）から遺伝子リストに含まれる生物学的機能を可視化し、直感的な分析が可能です。

##### マイクロアレイデータの準備
- サンプルデータとして、【実習2】で解析した遺伝子発現データを用います。このデータは、多重比較法（Benjamini & Hochberg）を指定して、有意水準1％未満かつ2倍以上発現差のあった遺伝子群のリストです。 

     → 「健常者＞AH患者_遺伝子リスト」[GEO2R_Ctrl.txt](https://github.com/AJACS-training/AJACS53/blob/master/yoki/GEO2R_Ctrl.txt) 
     
     → 「AH患者＞健常者_遺伝子リスト」[GEO2R_AH.txt](https://github.com/AJACS-training/AJACS53/blob/master/yoki/GEO2R_AH.txt) 
      
   （右クリックして「新しいタブで開く」もしくは「名前を付けてリンク先を保存」してください。）
  
- このデータから、どのような機能の遺伝子群に発現差があるのか、どのように解釈できるのかをDAVIDを使って考察してみましょう！  
 

####【実習3】DAVIDを使って、発現データの解析結果を生物学的に解釈する
- [【復習用】DAVIDを使ってマイクロアレイデータを解析する 2012](http://youtu.be/WIfe7Z_Mvxg)
- [【復習用】DAVIDの使い方 実践編](http://youtu.be/4f1t1ma9IRc)

1. 上部メニューの「Start Analysis」をクリックします。

  [![Gyazo](http://i.gyazo.com/dd857b29d9b70382ad81c314a5dbbed8.png)](http://gyazo.com/dd857b29d9b70382ad81c314a5dbbed8)

2. 画面左側バーで、「健常者＞AH患者_遺伝子リスト」のprobe IDをコピペ or ファイルを選択します。

  [![Gyazo](http://i.gyazo.com/6805eef66646ac24747a172d511afab6.png)](http://gyazo.com/6805eef66646ac24747a172d511afab6)

3. リストのIDの種類を選択します。 … 今回は、"AFFYMETRIX_3PRIME_IVT_ID" と "Gene List" を選択します。
4. Submit List をクリックするとリストが読み込まれます。

  [![Gyazo](http://i.gyazo.com/2b320b921e5c4854da042a74a93ebc8e.png)](http://gyazo.com/2b320b921e5c4854da042a74a93ebc8e)

5. アップロードしたリストは、コピペの場合、左側バーの "List Manager" で "List_1" として保存されています。ファイル選択の場合、「GEO2R_Ctrl」としてファイル名が表示されます。リストの削除やファイル名の変更もできます。

  [![Gyazo](http://i.gyazo.com/b95fed01af26ab455ce66aef0def467e.png)](http://gyazo.com/b95fed01af26ab455ce66aef0def467e)

6. バックグラウンドの種類タイプを選択します。 デフォルトでは "Homo sapiens" が設定されています。… 今回は "Human Genome U133 plus 2 Array" を選択します。

  [![Gyazo](http://i.gyazo.com/30d5fd8654f482c00b71a4328e8eee2c.png)](http://gyazo.com/30d5fd8654f482c00b71a4328e8eee2c)

7. バックグラウンドが変更されました。画面中央の「Functional Annotation Tool」をクリックします。

  [![Gyazo](http://i.gyazo.com/915313f2f422f7bfb36917f3f870dfb6.png)](http://gyazo.com/915313f2f422f7bfb36917f3f870dfb6)

8. Functional Annotation Tool のページが表示されました。"Gene Ontology" だけでなく、さまざまなアノテーション情報からの解析を閲覧できます。

9. 「Gene Ontology」をクリックすると、Gene Ontologyを用いた解析の細かいメニューが表示されます。

  [![Gyazo](http://i.gyazo.com/f8dea1e2599210e3968e6d950426b649.png)](http://gyazo.com/f8dea1e2599210e3968e6d950426b649)

10. 今回は、GOTERM_BP_ALL（BP = Biological Process）に注目します。「Chart」をクリックすると結果がポップアップされます。 

  [![Gyazo](http://i.gyazo.com/02c93e0cb523a671ed2c4132308e7948.png)](http://gyazo.com/02c93e0cb523a671ed2c4132308e7948)

11.  GOTERM_BP_ALL のチャートが表示されました。列見出しをクリックすると各項目でソートできます。「Download File」をクリックすると、結果をテキストで表示できます。 

  [![Gyazo](http://i.gyazo.com/c1dbf94268b2c67fee3f8754a6a9d706.png)](http://gyazo.com/c1dbf94268b2c67fee3f8754a6a9d706) 
 
13. 解析結果が表示されました。テキストファイルとして保存することも可能です。
 
  [![Gyazo](http://i.gyazo.com/a685f6594364770d21fd07e71aa02ab0.png)](http://gyazo.com/a685f6594364770d21fd07e71aa02ab0)

14. チャート画面の Genes の横棒グラフをクリックすると、その GOTerm に関連する遺伝子のリストが表示されます。… 今回は、 "alcohol metabolic process" の遺伝子リストを見てみましょう。

  [![Gyazo](http://i.gyazo.com/d2b26438ab88368bbda515967ef0c5dc.png)](http://gyazo.com/d2b26438ab88368bbda515967ef0c5dc)

15.  "alcohol metabolic process" の GOTerm に関連する遺伝子リストが表示されました。アップロードしたプローブ IDと、そのプローブに対応する遺伝子の名前がわかります。

  [![Gyazo](http://i.gyazo.com/bb6b9cd6a6abfe7a5358caed65cb530d.png)](http://gyazo.com/bb6b9cd6a6abfe7a5358caed65cb530d)

16. さらに、GOTERM_CC_ALL（CC = Cellular Component）や GOTERM_MF_ALL（MF = Molecular Function）を見てみます。
 　
 - 結果：GOTERM_CC_ALL
 
  [![Gyazo](http://i.gyazo.com/1034eeff59f505117a4f916b2517404c.png)](http://gyazo.com/1034eeff59f505117a4f916b2517404c)
 
 - 結果：GOTERM_MF_ALL
   
  [![Gyazo](http://i.gyazo.com/b5c425ba2babe4a1b8289f187bb18ea1.png)](http://gyazo.com/b5c425ba2babe4a1b8289f187bb18ea1)
 
17. Pathways > KEGG_PATHWAY や Tissue Expression > UP_TISSUE なども見てみましょう。
18. 同様に、「AH患者＞健常者_遺伝子リスト」も解析してみましょう。 

- 結果：GOTERM_BP_ALL
  [![Gyazo](http://i.gyazo.com/19b1cfa69b922d19949a18b936d65087.png)](http://gyazo.com/19b1cfa69b922d19949a18b936d65087)
- 結果：GOTERM_CC_ALL
  [![Gyazo](http://i.gyazo.com/427fe77cd38330271831aa43319b9ba3.png)](http://gyazo.com/427fe77cd38330271831aa43319b9ba3)
- 結果：GOTERM_MF_ALL
  [![Gyazo](http://i.gyazo.com/3081bcf0370882a4d39a851ce6626ffa.png)](http://gyazo.com/3081bcf0370882a4d39a851ce6626ffa)
 
- DAVIDで得られた結果を踏まえ、「健常者とアルコール性肝炎患者」の肝臓では、どのような違いがあるのか考察してみましょう。


----




