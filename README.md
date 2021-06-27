# CommonLit
<img width="950" alt="スクリーンショット 2021-06-26 5 14 01" src="https://user-images.githubusercontent.com/65795828/123480445-5443a300-d63d-11eb-8403-6ad3a02d0984.png">

機械学習は、テキストの一節の適切な読解レベルを識別し、学習を刺激するのに役立ちますか？読書は学業の成功に欠かせないスキルです。学生が適切なレベルの挑戦を提供する魅力的なパッセージにアクセスできるとき、彼らは自然に読書スキルを発達させます。

現在、ほとんどの教育テキストは、従来の読みやすさの方法または市販の公式を使用して読者と照合されています。ただし、それぞれに問題があります。Flesch-Kincaid Grade Levelのようなツールは、テキストデコードの弱いプロキシ（つまり、単語ごとの文字または音節）と構文の複雑さ（つまり、文ごとの数または単語）に基づいています。結果として、それらは構成概念と理論的妥当性を欠いています。同時に、Lexileなどの市販の数式は、コストが高く、適切な検証研究が不足しており、数式の機能が公開されていない場合は透明性の問題に悩まされる可能性があります。

CommonLit、Inc。は、2,000万人を超える教師と生徒に、3年生から12年生までの無料のデジタル読み書きレッスンを提供する非営利の教育テクノロジー組織です。アトランタのR1公立研究大学であるジョージア州立大学と協力して、彼らは可読性の評価方法を改善するようにカグラーに挑戦しています。

このコンテストでは、3年生から12年生の教室で使用するための文章を読むことの複雑さを評価するアルゴリズムを構築します。これを実現するには、機械学習スキルを、さまざまな年齢層の読者とさまざまなドメインから取得したテキストの大規模なコレクションを含むデータセットと組み合わせます。受賞モデルには、テキストのまとまりとセマンティクスが必ず組み込まれます。

成功した場合は、管理者、教師、生徒を支援します。パッセージを選択するリテラシーカリキュラムの開発者と教師は、教室の作品を迅速かつ正確に評価できるようになります。さらに、これらの数式はすべての人にとってよりアクセスしやすくなります。おそらく最も重要なことは、生徒は自分の仕事の複雑さと読みやすさに関するフィードバックの恩恵を受け、本質的な読解力の向上をはるかに容易にすることです。

### 評価
提出物は、二乗平均平方根誤差でスコアリングされます。RMSEは次のように定義されます。

<img width="248" alt="スクリーンショット 2021-06-26 5 18 41" src="https://user-images.githubusercontent.com/65795828/123480906-fb283f00-d63d-11eb-8282-0ef8e2303b8a.png">

ここで、\（\ hat {y} \）は予測値、\（y \）は元の値、\（n \）はテストデータの行数です。𝑦̂  は予測値であり、 𝑦 は元の値であり、 𝑛 テストデータの行数です。


### データ
このコンテストでは、文学からの抜粋の読みやすさを予測しています。いくつかの期間からの抜粋と幅広い読みやすさのスコアを提供しました。テストセットには、トレーニングセットよりもわずかに多い割合の最新のテキスト（一般化したいテキストのタイプ）が含まれていることに注意してください。

また、パブリックテストセットのライセンス情報が提供されていますが（関連する抜粋が表示/使用できるため）、非表示のプライベートテストセットには空白のライセンス/法的情報のみが含まれていることに注意してください。

ファイル
- train.csv-トレーニングセット
- test.csv-テストセット
- sample_submission.csv-正しい形式のサンプル送信ファイル

列
- id -抜粋の一意のID
- url_legal -ソースのURL-これはテストセットでは空白です。
- license -ソース資料のライセンス-これはテストセットでは空白です。
- excerpt -読みやすさを予測するテキスト
- target -読みやすさ
- standard_error-各抜粋の複数の評価者間のスコアの広がりの尺度。テストデータには含まれていません。

#### Train.CSV
No. |  Column |  Non-Null Count | Dtype  
-- | ----------- |  --------- | -----  
 0 |  id  |            2834 non-null |  object 
 1 |  url_legal   |    830 non-null  |  object 
 2 |  license     |    830 non-null  |  object 
 3 |  excerpt     |    2834 non-null |  object 
 4 |  target      |    2834 non-null |  float64
 5 |  standard_error | 2834 non-null |  float64

#### Test.CSV
No. |  Column |  Non-Null Count | Dtype  
-- | ----------- |  --------- | -----  
0   |id   |      7 non-null   |   object
 1  | url_legal | 3 non-null  |    object
 2  | license  |  3 non-null  |    object
 3  | excerpt  |  7 non-null  |    object

## Paper
No. | Name | Status | Detail | Date | URL
--- | ---- | ------ | ------ | ---- | ---
1|Getting started with Time Series using Pandas|ToDo|TimeSeries取り扱いnotebook|21/01/22|[url](https://www.kaggle.com/parulpandey/getting-started-with-time-series-using-pandas)
2|Time Series Analysis | ToDo | An Introductory Start(NoteBook) | 21/01/22 | [url](https://www.kaggle.com/janiobachmann/time-series-analysis-an-introductory-start)

## NoteBook
### CommonLit_001
21/06/25
Public 0.760
- ベースライン
[TF-IDF_XGBOOST](https://www.kaggle.com/w1023672708/tfidf-xgboost)

### CommonLit_002[(url)](https://www.kaggle.com/kazumaishibashi/commonlit-002)
21/06/26
Public 0.747
- 特徴量にワードカウント追加
- Testデータが少ないのでCVstrategyを先に考える
- [StratifiedShuffleSplit](https://www.kaggle.com/kazumaishibashi/train-val-split/edit)

### CommonLit_003[(url)](https://www.kaggle.com/kazumaishibashi/commonlit-003)
21/06/26
val 0.413
Public 0.760
- validation追加
- train_dataのみでtfidf
- valの予測は意外と良くできている
<img width="406" alt="スクリーンショット 2021-06-27 6 51 26" src="https://user-images.githubusercontent.com/65795828/123526619-19f90500-d714-11eb-89c1-207b36b9d864.png">

### CommonLit_004[(url)](https://www.kaggle.com/kazumaishibashi/commonlit-004)
21/06/26

ver1:LGBM, val=StratifiedKFold(n_splits=5,shuffle=True,random_state=42), 上記StratifiedShuffleSplitで作成したtrainデータでtfidfコーパス作成
- val 0.766, Public 0.733

ver2:全てのtrainデータでtfidfコーパス作成
- val 0.763, Public 0.734
