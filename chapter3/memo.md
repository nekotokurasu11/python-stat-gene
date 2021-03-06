# 6/20の勉強会

### 第三章
### 統計学入門
調査によって得られた数量で現象を把握すること  
  
リアルワールドの事象は簡単に記述できない。  
統計学には12個の分野がある。  
  
統計学分野の5つの特徴  
  
- 解析対象の因果関係が担保されているケースが多い  
- 膨大な数の検定を一つに行う必要がある。  
- とてつもなく小さなp値を用いる。(表計算ソフトでは無理)  
- 圧縮されたゲノムデータを解析に使用する  
- 検定統計量の分布を理論的に定義できない。  

Tips  
 : 生命科学実験の有意水準は通例、α=0.005,0.1
 : p値が低いのは掛け算が何度も行われている。

#### 母集団・標本集団
母集団 : 現象を構成するデータ全体の集まり  
標本集団 : 母集団から取り出して観測されたデータの集まり  

統計学でも用いるのはもちろん標本集団  
  
Tips : From Data to Viz  
  
- 正規分布
- t-分布
- x^2分布
- F分布
- ポアソン分布
  
#### 帰無仮説とp値
Q,イカサマコインを探せ  
古典的仮説検定  
  
帰無仮説 : 効果がない、差がないなど、主張したいこととは反対の仮説  
対立仮説 : 帰無仮説と反対の仮説、本来主張したい仮説  
  
統計検定の流れ  
1.帰無仮説が成立すると仮定する。(コインだと1/2で出るよ)  
2.上記の仮定の元で、観測された自称よりも極端な事象が発生する確率を計算  
3.著しく稀な観測値が得られた場合（p値が小さい）  
4.帰無仮説は正しくない（棄却される）  
5.対立仮説が成立する。  
  
p値 : 帰無仮説下で、今回の観測結果以上の統計検定量が得られる確率  
  
GWASにおける有意水準は5.0E-8のようなかなり小さい値を設定する。
  
有意水準を補正する必要がある  
ボンフェローニ補正　：有意水準を検定数で割った値とする。(これでp値が小さくなる)  
  
p値というのは、偏りを意味する値ではない。  
  
Tips
 : 統計的有意性と P 値に関する ASA 声明（Neatureダイジェスト）
 : 日本でも出ている（日本軽量生物学）
  
↓
ただ、研究分野では、なんやかんやp値に頼ってしまうところがあるらしい。

#### t検定
2郡の平均値に有意差があるかどうか。  
  
t検定の流れ  
  
- 2郡の平均値に有意差はあにと仮定（帰無仮説）
- 帰無仮説の仮定のもとで、観測された自称のt値を計算
- t分布からt値をp値に変換
- p値が有意水準より小さい場合、無帰仮説は棄却される
- 有意差があるという対立仮説が成立する。
  
  
カイニ乗検定  
  
カイニ乗検定の流れ  
  
- 観測された度数分布と理論分布の差の検定
- 観測された度数分布と、帰無仮説の仮定した場合の理論分布x^2値を計算
- カイ二乗分布によりx^2値をp値に変換
- p値が有意水準より小さい場合、帰無仮説は棄却される
- 2つの変数は独立ではない、つまり2つの変数間には関連があるという対立仮説が成立する。

カイニ乗分布の形は、自由度を決めると決まる  
m行n列のクロス集計表の場合の自由度(m-1)(n-1)  
2行2列の場合、自由度 (2-1)(2-1)=1  
  
分割表の度数が小さい場合  
補正方法があるが、補正しすぎる時がある。  
  
相関係数  
分布もみた方がいいで  
  
線形回帰  
xの値から連続変数yの値を予測する回帰問題で使用  
pythonのソースではOLS?を使ってくれた
  
ロジスティック回帰  
一般的に2クラス**分類問題**に使用  
目的変数：yは0または1の二値  
予測値（式パッとかけない）  
0~1の間の値をとる確率とみなすことができる  
※一般化線形モデル
  
  
p値ハッキング  
検定手法が異なれば、異なるp値が得られる  
「p値がなるべく小さくなる検定手法を選ぶ」**ダメ・絶対！！**

