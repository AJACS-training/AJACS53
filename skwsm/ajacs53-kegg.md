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
- KEGGを主幹とするデータベース群と、それらデータを解析するための計算ツール群からなっている

### KEGG 概要

- ゲノムや分子レベルの情報から細胞、個体、エコシステムといった生命システムレベルの機能を整理したデータベース
- 遺伝子や化合物などの分子部品のデータベースと、それらをつなぐネットワークのデータベースからなっている

[!Fig1(https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_overview1.png)](https://github.com/skwsm/AJACS53/blob/skwsm-work/skwsm/images/AJACS53_KEGG_overview1.png)

### KEGG Organism

### KEGG Genes

### KEGG Orthology (KO)

### KEGG Pathway

### KEGG Module

### KEGG Mapper

####[KEGG Mapper: http://www.genome.jp/kegg/mapper.html](http://www.genome.jp/kegg/mapper.html)

- Pathway, BRITE, Module などへ、指定した遺伝子、

####【実習1】LinkDBを用いて、データベースIDの変換を行う。

####【実習2】KAASを用いて、自動遺伝子アノテーションを行う。

####【実習3】KEGG Mapperを用いて、パスウェイ再構築を行う。