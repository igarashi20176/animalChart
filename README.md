# animalChart
This is My first vue creation / 2022/09/25 ~ 

### ◆作品の概要
このアプリは, 譲渡に出されている動物たち(犬・猫)を閲覧できる機能とともに, 飼い主が動物に飼う適性があるかどうかを診断する機能を備えました。
動物たちを"可愛い"という理由だけで飼うのではなく, 飼い主が金銭・時間等も十分に持ててるかどうかを診断します。

### ◆作ることになった動機(~未編集~)
保健所が公開する犬や猫の取引　そのうち1割程度は飼い主からの引き取り　それ以外は引き取り元不明である　つまり9割程度が野良の犬や猫  
一割と言っても, その譲渡数は3000匹程度と決して無視できるような数ではないし, 律儀に保健所に直接渡す人がいるとも限らない。要するに, ペットを許可なく捨てる飼い主もいるのが現状。
飼い主には, もっとペットを飼うためのモラルや飼えるかどうかの自覚ができる指標が必要だと考える。

### ◆各View, Componentの概要
以下のサイトを参考に, 機能的なアプリを作るよう心掛けました。  

【Vue】単一ファイルコンポーネントの命名規則まとめ【ファイル名から記法まで】  
https://qiita.com/ngron/items/ab2a17ae483c95a2f15e  
【React/Vue.js】コンポーネント設計の（個人的）ベストプラクティス  
https://zenn.dev/offers/articles/20220523-component-design-best-practice   

#### ○App.vue
&ensp;アプリの基本となる画面の構成を担います。一連の画面遷移による画面描写はApp.vue上で行われます

#### ○AnimalList.vue
&ensp;動物たちのリストを表示するためのContainer(入れ物)としての役割です。  
&ensp;後述するListItem.vueとは, Container ⇔ View(ステートレスで受け取ったpropsのみで機能する)の関係です  
 - App.vueからroute.paramsを受け取った場合, お気に入り登録されている動物のリストをListItem.vueに渡します

#### ○AnimalListItem.vue
&ensp;親コンポーネントであるAnimalList.vueから動物たちのリストを受け取り, それらを表示します。
 - 診断チャートを行っていた場合, 診断結果である飼い主適正ランク(A~D)に基づき, 利用者がどの動物を飼えるかどうかも表示します。(難易度表示)

#### ○AnimalListDetail.vue
&ensp;AnimalListItem.vueのリストがクリックされた際に, そのリストの詳細を表示します

#### ○AnimalChart.vue
&ensp;後述するChartList.vueとは, Container ⇔ Viewとの関係です。診断チャートを表示 & 診断結果を表示します

#### ○ChartList.vue
&ensp;診断チャートの各問を表示します。動的に...

#### ◆各parts(最小粒度のコンポーネント)の概要
 - btn-primary
