# 森林成長予測システム　Foredict

## ver.1.0.0
![表紙画像](https://user-images.githubusercontent.com/34940116/99905892-184b0700-2d17-11eb-9b4e-32e8cbd284c7.jpg)

-----------------------------------------------------------------------------------------------------------

## 機能概要

本システムは、密度理論を用いた成長モデルにより森林の成長予測を行います。既存の密度管理図では、無数のグラフが入り乱れており、林業経営者にとって扱いがとても難しいものです(専門の林業技術者でも慣れるまで時間を要しますね…）。そのため、本システムでは、林業経営者の皆様が森林の造成計画を立てるにあたり、森林の成長をより直感的にわかりやすく予測できるようにすることを目的として作成しました。

-----------------------------------------------------------------------------------------------------------

## 使い方

1. パラメータ入力

　　森林の成長予測を行うにあたり、成長予測に用いるパラメータが必要になります。
　　パラメータ入力シートで、成長を予測したい森林がある地域に合わせて、地域ごとに作成されている既存の密　度管理図のパラメータを入力してください。
　　一般的にweb上で公開されている、システム収穫表等は、地域で限定されてしまっていますが、本システム　　では、パラメータを自由に設定できるため、様々な地域の森林の成長予測に用いることが可能となっておりま　す。もちろん、自分でチューニングしたパラメータを用いることも可能です。
　　どのパラメータを変えると、どのように森林の成長挙動が変わるかもシュミレーションできるので、密度管理図
　の難解な式の理解にも役立てることができます。森林について学習中の方々も自由気ままに使ってみてください。

2. 森林の現況を診断する。

　　この機能は、現時点で存在している森林の間伐の必要性について林齢と樹高と密度を入力することで、間伐不要・要間伐・手遅れの３段階で診断することができます。手遅れについては、幾分語弊があるかもしれませが、相当程度に過密化が進み自然枯死が進んでしまった林分です。
　　なお、本機能により、間伐のみならず地位指数・地位も算出することができますので、その林分の成長の良し悪しについても評価することが可能になっています。
　　本機能の使い方としては、４行目にいくつかの項目がありますが、オレンジ色に塗られたセルの林齢・樹高・密度の３項目について入力した上で、現状を診断するをクリックするだけです。

![現状診断実行前](https://user-images.githubusercontent.com/34940116/99941240-09b12e00-2db1-11eb-8d75-27e55fcab3a5.jpg)
現状診断の実行前画面

![現状診断実行後](https://user-images.githubusercontent.com/34940116/99941291-2188b200-2db1-11eb-8e0c-0f43503926cf.jpg)
現状診断の実行後画面

3. 森林の成長を予測する。

　　この機能は、質問事項に沿って条件を入力することで、予定伐期までの森林の成長を予測するシステムです。
　　使い方は２つあります。一つ目が、林齢０年から成長を予測するもの。もう一つがある程度成長している森林がこれからどのように成長していくかを予測するものです。いかにそれぞれの方法での使い方を解説します。

**林齢０年からの成長予測**

質問事項の「林分の現在の林齢を入力してください」欄に０を入力します。次に、「間伐の予定年を入力してください」欄に間伐予定年をカンマ区切りで入力してください。また、間伐予定年の入力回数に合わせ、「予定本数間伐率を入力してください」欄に、間伐率をカンマ区切りで入力してください。そして「伐期林齢を入力してください」、「植栽本数を入力してください」、「地位指数を入力してください」欄それぞれに、条件値を入力してください。以上の項目の入力が完了したら、予測を開始するボタンをクリックしてください。そうすれば、質問事項右側の出力スペースに予測結果が出力されます。また、ユーザー設定作業の右側に何も施業を行わなかった場合の成長予測が出力されるようになっており、ユーザー入力した施業を行った場合の成長と、何も施業を実施しなかった場合の成長予測の比較ができるようになっています。

![成長予測実行前](https://user-images.githubusercontent.com/34940116/99941356-3bc29000-2db1-11eb-962a-c003d36f0049.jpg)
成長予測実行前画面

![成長予測実行](https://user-images.githubusercontent.com/34940116/99941391-4da43300-2db1-11eb-814e-eef5c9f8edb6.jpg)
成長予測実行結果画面

**ある程度成長している森林のこれからの成長を予測する場合**

質問事項の「林分の上層木平均樹高を入力してください」、「林分のhaあたり本数を入力してください」、「間伐予定年を入力してください」、「予定本数間伐率を入力してください」、「伐期林齢を入力してください」の欄に、これからの成長を予測したい林分の値を入力してください。今回の予測方法では「植栽本数を入力してください」、「地位指数を入力してください」の欄の入力は不要です。以上の入力欄に値を入力した上で、予測を開始するボタンをクリックすれば、予測結果が出力されるようになっています。
　　  
　　
4. 成長の予測結果を可視化する。

　　3.で森林の成長予測結果を出力したら、大量の数字が並んだかと思います。実際数字が並んでいるだけでは、成長の違いがイメージしにくいため、成長の違いを可視化する機能を２つ実装しています。一つ目が、伐期時点に置ける丸太の断面図を出力する機能、もう一つが成長の過程をグラフ化する機能です。以下の機能については、ボタンでの配置はしておらず、開発タブからマクロの実行により実行することができます。（今後のアップデートでボタンの配置を行う予定です。）

**丸太の断面図を出力する機能** 
以下の写真のように、新しいワークシートが自動で生成されそこに、ユーザーが設定した施業と無施業の場合でのそれぞれの断面図が出力されます。10年毎の直系の数字も出力され、10年単位での成長の差を確認することができます。

![断面生成実行](https://user-images.githubusercontent.com/34940116/99941461-67457a80-2db1-11eb-89a4-84448c89873d.jpg)
丸太断面図の出力結果画面

**グラフを生成する機能** 

以下の写真のように、丸太の断面図の出力と同様に新たなワークシートが出力され、そこにユーザーが設定した施業とむ施業の場合での成長の過程を比較したグラフが出力されます。（今後のアップデートで、ユーザーが比較したい次元でのグラフを自由に設定できる機能を実装する予定です。）

![グラフ作成](https://user-images.githubusercontent.com/34940116/99941517-7c220e00-2db1-11eb-8f0d-ce10503661e3.jpg)
グラフの生成結果画面

5. foredictに施業を提案してもらう。

　最後にforedictに施業を提案してもらう機能について説明します。おそらく、本システムの利用者さんは、適切な密度で森林の成長を推移させるためにどのように施業を行うべきかを何通りもシュミレーションするために本システムを利用するかと思います。そこでシュミレーションする手間を軽減するため、どのような施業を行えば良いかを利用者の判断基準に合わせて出力する機能を実装しました。
 使用方法としては、質問事項に自分がこれから造成しようとしている森林の条件値とどのような基準で施業を行っていきたいかを入力してください。施業提案基準については、相対幹距と収量比数の２つから選択することが可能です。
![施業提案実行前](https://user-images.githubusercontent.com/34940116/99941574-99ef7300-2db1-11eb-80e1-c69795ea2b80.jpg)
施業提案実行前画面

![施業提案実行後](https://user-images.githubusercontent.com/34940116/99941580-9bb93680-2db1-11eb-91cd-96879408ba37.jpg)
施業提案実行後画面１

![施業提案実行後２](https://user-images.githubusercontent.com/34940116/99941584-9d82fa00-2db1-11eb-9a4d-ac0976702da9.jpg)
施業提案実行後画面２