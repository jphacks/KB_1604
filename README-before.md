# IoK(Internet of Keys)

- こちらは、HackDayよりも前に開発を開始する際に利用してください
- HackDay前に企画した内容・開発した内容について記載してください

## 製品概要
### Key Tech

### 背景（製品開発のきっかけ、課題等）
戦後インターネットの急速な普及に伴い、インターネット接続端末は急速に小型化・量産化されてきた。半導体技術が進化しそれらが可能になる技術的基盤が整うことによってIoT(Internet of Things)が注目されることは容易に想像できたことである。イノベーションとしてみれば、インターネットは情報を最も早く届けることを可能にしてしまっためこれ以上時間軸による性能の向上は期待できない。ともすれば量的または空間的な情報の伝達の方面にフロンティアの目は向く。そうして社会のニーズによって生まれたIoTはそれらの性能を一挙に向上させてしまうだけの可能性のあるテクノロジーである。人間の体感時間で情報の伝達がほぼゼロになった今、人類はその情報の中身にまで効率化の手を伸ばしたのである。
IoTブームの到来とともに個人単位でも低コストでIoT環境を構築することが可能になってきた。マイコンはモジュール化がすすみ高性能になりつつ周辺モジュールが豊富になっていった。IoTを手軽に実現するためのクラウド上のプラットフォームも各社がサービスを開始し、それに伴いドキュメントや実装例などの実績も増えていった。数人のプロジェクトで短期間で実装できるシステムと考えたとき、これらの技術は適度な新規性と技術的難易度を有するのである。本プロジェクトはこの技術をどう活用するかという発想のもと提案された。
IoTは情報の発信と活用の概念であり、応用範囲はほぼ無限に存在する。さらにはDeepLearningを初めとする柔軟な情報処理手法も発展しIoTと相互にリンクすることでイノベーションは更に加速された。それ故に様々な提案がなされ、中にはありふれたアイデアというものも少なくはない。それらの中でブレインストーミング等を行った。技術的・時間的制約により、身近でシンプルな、ちょっとしたニーズに低コストで対応できることを主軸として考え、ヒューマンエラーをテクノロジーで解決しようという着想のもとkey×techを生み出した。
key×techは鍵の締め忘れを技術で防ごうという着想である。家の玄関の鍵の状態を監視し、締め忘れの可能性が高い状況でスマホのアプリ経由で注意喚起を行ったり、外出先で家の鍵の状態を確認できるようにするシステムである。これにより鍵の締め忘れという課題に対して事前・事後解決という方法で解決を図っている。身近でシンプルなという着想から、導入する機器の大きさ・価格・設置の手軽さ・には終始配慮したシステム設計を行っている。
応用例として、これにIoTが加わると鍵の締め忘れ以外の他の課題の解決に繋がるのである。家に住んでいる人はおおよそ自分の家の開閉が行われる時間や状況を把握している。これにより泥棒の可能性が高い場合に警告したり、複数のスマートフォンと連携し鍵を開閉した人を識別することで子どもの帰宅の確認をしたりすることもできる。宅配業者と連携をすれば中に人がいる時間帯を予測して通達することも可能になる。総じて家における人の出入りをセンシングすることができるだろう。スマートフォンに依存した人物検知システムが蔓延する中、場所的制約は存在するがスマホが機能しない状況でも人の不在を検知できることは独自のメリットになるのではないだろうか。


### 製品説明（具体的な製品の説明）
本システムは鍵の状態を検知するデバイスと、その状態を表示するスマートフォンアプリによって構成される。鍵の検知には
* 電磁誘導型
* タクトスイッチ型
* 傾斜スイッチ型
* 磁力スイッチ型
などが考えられたが、既存のドアの鍵により多く対応するため、磁力スイッチ型を採用した。設置の方法としてはデッドボルトとその周辺にシートを貼るだけである。デッドボルトに貼るシートには中にネオジウム磁石が入っており、その周辺に貼るシートにはリードスイッチ(磁気スイッチ)が入っている。周辺に貼るシートからは銅線が出ており、それが本体に伸びている。本体は内側のドアに貼り付けることで設置できる。リードスイッチの状態により鍵の施錠状態を検出する。シートの厚さ・銅線の太さともに一般的なドアに設置できるよう十分薄くしている。本体の中にはarduinoマイコン・wifiモジュール・電池・スイッチ等が入っている。

主に次の機能が使える
* 今の鍵の施錠状態を表示する
* 時系列順に、鍵を開け閉めした時間を表示する
* 鍵の締め忘れを予測して通知を行う

データを本体に保存するか、各スマホに保存するか、クラウドに保存するかは現在検討中

### 特長
####1. 特長1 価格の安さ
大手通販メーカーなどで出回っている施錠状態検出システムを内蔵する製品は安くても10000円程度であり、ちょっとしたニーズである割には導入の敷居が高い。導入の手軽さという観点から本システムは開発段階で原価を1000円程度に抑えた。
####2. 特長2 導入の手軽さ
本体の設置も2枚のシートを張り、本体を扉に貼り付けるだけで完了する。それで十分精度が確保されるようにシートも工夫をしている。また初期設定もアプリから必要最低限の情報を入力するだけで完了させている。またアプリの表示インターフェースも、他のアプリからの情報を埋め尽くさないよう最低限の通知を主とし、操作に時間を取られないよう、アプリを起動すればいきなり表示画面に移行するよう設計している。

### 解決出来ること
* 鍵の締め忘れの防止
* 家族の帰宅情報の取得

### 今後の展望
* 現在、アプリケーションの持つ本体のURLや本体がもつ家のルーターのSSIDやパスワードはプログラムで直打ちしている。将来的にはスマホとモジュールをwifiで接続した段階で自動的に通信を行なわせる。
* 現在、自宅からどれだけ離れたのかという指標に本体からのスマホが検知する電波強度を使用している。これだと自宅の外と内の区別がつかないため、将来的にはスマホ内のGPS情報を用いて自宅からの距離を算出する。
* 現在、アプリが起動している間のみセンサの状態を監視している。これをバックグラウンドで起動させることで常に監視するように設計する必要がある。
* 現在、鍵の状態の履歴はスマホ側で管理している。これだとスマホ内でアプリが起動していない間のデータが欠落してしまう。将来的にはクラウド上にデータを保管し、アプリ起動時にはそこから履歴データを持ってくる。
* 現在、鍵の状態の監視は一定時間ごとに行っているがこれだと通信量が肥大化する。将来的には本体側で状態の切り替えが起きた時のみデータを発信するようにする。また本体を常にスリープモードにしておき状態の切り替えが起きた時のみに起動することで1〜5日程度しか持たない電池を一ヶ月程度もたせることが可能になる。
* 現在、本体が検知するデータは鍵の施錠状態のみである。将来的にはアプリの初期設定の時にユーザー情報を取得し、鍵の切り替えが行われた時に玄関から一定の距離以内にいる人のユーザーIDとともにデータを管理する。これにより誰が鍵を開けたのかというデータを取得することができ、アプリに表示する情報を増やすことができる

### 注力したこと（こだわり等）
* アイデア出し、開発途中、発表準備におけるすべての段階で実際のビジネスとして応用することを考慮した。開発だけではなく、本体の低コスト化や競合他社の調査・初期設定の手軽さなどにも注力した。
* 本システムがどんな社会的問題を解決できるのか、このシステムは社会にでるべきなのかという論点から、利益一辺倒ではないビジネスモデルの考案を心がけた。このシステムを開発するにあたって、鍵を締め忘れたかどうかわからなくなった時の不安さや子どもを持つ親の気持ちをどうにかしようというモチベーションが根底にはある。

## 開発技術
### 活用した外部技術
#### API・データ

#### フレームワーク・ライブラリ・モジュール
* arduino IDE
* arduino library(nortification library)
* android studio
* android library(GPS library)
* java library(http library)
* And Elder,apach lisence v2,https://developer.ibm.com/recipes/tutorials/connect-an-esp8266-with-the-arduino-sdk-to-the-ibm-iot-foundation/

#### デバイス
* ALE-02L, EMUI4.0, android 6.0
* ESP 8266

### 独自技術
#### 期間中に開発した独自機能・技術
* ESP 8266 という通信モジュールを用いた低コストwifi環境の構築（回路作成）
* 一般的な扉に設置可能な鍵施錠状態検出センサの開発
* wifiの電波強度を用いてスマホの位置の屋内・屋外を判別するシステムの開発
* GPSと鍵の施錠状態から鍵の締め忘れを推測するシステムの開発
