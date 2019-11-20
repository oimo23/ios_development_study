<h1 align="center">:iphone: iOS開発/Swift に関して勉強した記録</h1>
<p align="center">
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/Author-oimo23-brightgreen.svg?style=flat-square" alt="Author oimo23">
  </a>
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/18276888/67656087-2274c780-f996-11e9-9e1e-5605a5a48256.jpg" width="250">
</p>

iOS開発/Swiftについて勉強した記録をするリポジトリです。  
以下のドキュメントは時系列順ではなく、勉強カテゴリ別です。  
    
・Repl.itというオンラインエディタ上で実験した  
・AtcoderのAB問題を50問解いて文法の練習をした  
・Xcode上でプロジェクトを作った  
・プロのコードレビューを受けた  
・Bitriseを使ってみた  
・アプリストアに自作アプリを公開した  
・上の中には書いていない、勉強の中でつまづいたところとそれに対する自分なりの理解を書いた  
・今後勉強したいこと  
    
という構成です。
    
    
## 基礎的な文法をRepl.it上で勉強
<p align="center">
  <img src="https://user-images.githubusercontent.com/18276888/67656472-3b31ad00-f997-11e9-9f9a-048a6ad7beac.png">
</p>
手軽にSwiftを動かせる環境として、Playgroundも良かったが共有も簡単な [Repl.it](https://repl.it/) というオンライン上で使えるエディタのWebサービスを活用した

### 目的別にググって出てくる記事を見ながらrepl.it上で手を動かして確認した
下記に文法名とリンク先に実際書いて勉強したコード  

#### :white_check_mark: 変数/定数宣言  
https://repl.it/@oimo23/Bian-Shu-Ding-Shu  

#### :white_check_mark: 配列  
https://repl.it/@oimo23/Pei-Lie    

#### :white_check_mark: 関数定義  
https://repl.it/@oimo23/Guan-Shu-Ding-Yi  

#### :white_check_mark: ループの書き方  
https://repl.it/@oimo23/Zao-riFan-si
 
#### :white_check_mark: Math系  
https://repl.it/@oimo23/MathXi    

#### :white_check_mark: map,reduce,filter  
https://repl.it/@oimo23/map-reduce-filter

#### :white_check_mark: sort  
https://repl.it/@oimo23/sototoreverse

#### :white_check_mark: struct  
https://repl.it/@oimo23/Structtoha

#### :white_check_mark: optional型について  
https://repl.it/@oimo23/Optionaltoha

### :white_check_mark: Struct
https://repl.it/@oimo23/Structtoha

### :white_check_mark: ClassとEnum
https://repl.it/@oimo23/ClasstoEnum

### :white_check_mark: Exteinsion
https://repl.it/@oimo23/extensiontoha

### :white_check_mark: 循環参照とメモリリーク
https://repl.it/@oimo23/Xun-Huan-Can-Zhao-tomemoririku

### :white_check_mark: Protocolとは
https://repl.it/@oimo23/Protocoltoha

### :white_check_mark: ProtocolでのExtensionによるデフォルト実装
https://repl.it/@oimo23/ProtocolnoextensionwoLi-Yong-sitadehuorutoShi-Zhuang-nituite
    
    
## AtcoderのAB問題を50問解いて体に馴染ませてみた
<p align="center">
  <img src="https://user-images.githubusercontent.com/18276888/67656575-877ced00-f997-11e9-879b-6c34d818e034.png">
</p>
プログラミング言語の文法を体に身に付かせるのはAtCoderのAB問題をやるのが一番良いと思った経験からやってみた
   
[そのリポジトリ](https://github.com/oimo23/Atcoder_Swift)

#### :white_check_mark: 得られたこと  
Repl.itで学んだことが体に馴染んだ  

#### :white_check_mark: 新たに気付いたこと  
0除算をするとバグる  
配列に対するmax()など　返り値がoptionalなやつがあるので注意しないといけない    
optionalの安全なunwrapは guard let unwrapped = mayOptional else { return }    でやる？

    
## Xcodeでのアプリ開発
### Hello Worldアプリを作った
![イメージ](https://user-images.githubusercontent.com/18276888/64484545-9de7b180-d24e-11e9-946e-c4e23be1a321.GIF)  
本当にテキストと画像が出るだけ  

#### :white_check_mark: 得た知識  
・アイコンの設定の仕方  
・アイコンは解像度別に何種類か用意してあげないといけないこと  
・[appicon generator](https://appicon.co/)というサイトがアイコン作るのに便利だということ  
・StoryBoardを使うとPhotoshopとかみたいにGUIでTextやImageを簡単に配置出来た  
・SEでビルドしたら、左上がクロッピングされた感じになった ➡︎ AutoLayoutを使えばとりあえず良いと知った  


### クイズアプリを作った
![イメージ 2](https://user-images.githubusercontent.com/18276888/64484552-a04a0b80-d24e-11e9-8cc3-19da51a97163.GIF)  

### おみくじアプリを作った
![イメージ 3](https://user-images.githubusercontent.com/18276888/68604662-54d20900-04ee-11ea-82ac-84b4ac6a85ef.GIF)  
[そのリポジトリ](https://github.com/oimo23/Omikuji)

#### :white_check_mark: 得た知識  
・CocoaPodsの使い方、またそれを利用したサードパーティのライブラリの使い方を知った
・SwiftLintの使い方を知った  
・MVC、MVPのディレクトリ構造　設計の仕方を自分なりにだが解釈できた  
・XCTestを用いたユニットテストのやり方を知った

### お天気アプリを作った
![イメージ 3](https://user-images.githubusercontent.com/18276888/65624508-05e71780-e005-11e9-85d5-635427e8a696.GIF)  
[そのリポジトリ](https://github.com/oimo23/oTenki)

#### :white_check_mark: 得た知識  
・Alamofireを使ってAPIを叩く方法を知った  
・APIから貰ったJSONを整形して画面上に表示する流れを知った  
・CoreLocationで位置情報を利用する方法を知った  
・Delegateの使い方を知った  

### Todoアプリを作った
![イメージ 3](https://user-images.githubusercontent.com/18276888/65648805-cdfcc600-e03e-11e9-8790-bf8e29beeca6.GIF)  
[そのリポジトリ](https://github.com/oimo23/Todo)

#### :white_check_mark: 得た知識  
・Realmを使ってローカルにデータを永続化する方法を知った  
・テーブルの使い方を知った  

## プロのコードレビューを受けた
あるサービスで現場で開発しているiOS開発者にコードレビューを受けた。  
有償でやってもらったので、詳細はこのリポジトリには記述しないが、大まかに
    
・JSONのデコードは自分はSwiftyJSONを使っていたが、JSONDecoderを使うのが一般的ということ  
・プロジェクト全体で使うConstantな値の管理は、Singletonパターンを適用すると良い  
・クロージャ内のselfは[weak self]で弱参照にしないと循環参照になる  
・メインスレッド以外で画面更新を行おうとすると失敗するかクラッシュする  
・自分が書いていたAPIClientモデルの書き方の改善例  
   
などの知見を得ることが出来た。  

## App Storeにアプリを公開した
[フリマプリ便利計算機](https://apps.apple.com/us/app/%E3%83%95%E3%83%AA%E3%83%9E%E3%82%A2%E3%83%97%E3%83%AA%E4%BE%BF%E5%88%A9%E8%A8%88%E7%AE%97%E6%A9%9F/id1482937342?ign-mpt=uo%3D4)
    
アプリ公開までの流れを知りたくてまずリリースしてみた。  
とてもシンプルなのでMinimun Functionsで弾かれるかと思ったが無事審査に通過出来た。 
    
・Developerライセンスの取得  
・アプリのアーカイブ  
・証明書の設定   
・リリース時の情報記入の方法   

など実際にリリースする流れを掴むことが出来た    

## Bitriseを使ってみた
GitHubのリポジトリと連携して、指定したブランチにpushがあったらBitrise側で設定したWorkflowを実行するやり方を知った。  
Testの実行と、プロジェクトのアーカイブ、iTunes Connectへのデプロイまで自動化出来た。  
     
基本的なBitriseの知識不足、証明書関係のエラーが出まくり、１週間くらいハマってアプリ自体の開発より辛かった。  

## iOS開発 / Swift の勉強でつまづいた所と自分なりの答え
#### :question: Optional型  
Swift特有でとっつき辛かった  
nil (null) が入っているかもしれない型のこと  
Swiftではnilはちゃんと扱わないとアプリが落ちるようだ  
String? なら、Stringかnilを許容する  

StringとString?は型としては完全に別のもの  
Optional型から値を取り出すときにはUnwrapという作業が必要になる  

#### :question: 強参照、弱参照  
最初はまったく理解出来なかったが、何回もググったり、Repl上で実験したりコードレビューを受けて少し理解出来た。  
循環参照によるメモリリークを防ぐために、弱参照を使用するのだと理解した。  
クロージャが絡むと出てくる気がする。  

#### :question: Delegate  
delegateはかなり理解に苦しんだけど、実は単にUITextFieldなどのクラスが持っているプロパティ名だと思う。  
何かイベントを起きたことを通知してUIViewController側でそれを利用して処理をしたいときに、delegateにUIViewControllerを指定しないと使えない。    
そしてUIViewController自身もUITextFieldDelegateに準拠していなければいけないということだと思う。  

#### :question: Protocol
classやstructがどんな関数や変数持ってるか指定するものだと理解した。  
普通の変数に対して型が指定されるのに対して、classやstructにはprotocolを指定してやるという事だろうか。  
    
単にふるまいを定義するだけでなく、デフォルト実装というものも指定出来ると後から知った。  

#### :question: Lazy
参照されるとき初めて初期値が設定されるらしい  
メモリの節約のため？ 画像で言うところ必要な時まで読みこまない lazy load 的な発想から lazy って名前なのだろうか？  
正直よく分かっていない   

#### :question: guardってなに？  
Optional型の安全なunwrapの時に使うものと理解した  

#### :question: cocoapodsってなに？  
パッケージ管理をしてくれる  
npmみたいなもの   

pod init でファイルが出来て、そこに必要なパッケージの名前を書いて cocoapod install すると入れてくれる  
    
ファイル内で「import ○○」と書くと使えるようになる  

#### :question: 関数の引数のところに付いているアンダースコア(_)は何？  
_ をつけると引数名を省略出来るらしい
func numberThreeTimes(_ num: Int) -> Int {
  return num * 3
}

numberThreeTimes(2) // これで良くなる

#### :question: xcodeproj xcworkspaceの違い  
よく分かっていない  
cocoapodを使うとxcworkspaceで開く必要があるようだ  

#### :question: classの前の final ってなに？  
finalをつけるとそのクラスは継承されないことが保証されるらしい  
    
## これから頑張りたいこと
-RxSwift

-ProtocolやEnumを活用したSwiftを有効活用した書き方を使えるようになりたい

-SwiftUI
