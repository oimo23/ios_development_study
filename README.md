# :iphone: iOS開発/Swift に関して勉強した記録

iOS開発/Swiftについて勉強した記録をするリポジトリです。  
以下のドキュメントは時系列順ではなく、勉強カテゴリ別です。  
    
・Repl.itというオンラインエディタ上で実験したこと  
・AtcoderのAB問題を50問解いて文法の練習をしたこと  
・Xcode上でプロジェクトを作ったこと  
・プロのコードレビューを受けたこと  
・アプリストアに自作アプリを公開したこと  
・上の中には書いていない、勉強の中でつまづいたところとそれに対する自分なりの理解  
・今後勉強したいこと  
    
という構成です。

## 基礎的な文法をRepl.it上で勉強
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

### :white_check_mark: 循環参照とメモリリーク
https://repl.it/@oimo23/Xun-Huan-Can-Zhao-tomemoririku

### :white_check_mark: ProtocolでのExtensionによるデフォルト実装
https://repl.it/@oimo23/ProtocolnoextensionwoLi-Yong-sitadehuorutoShi-Zhuang-nituite

    
## AtcoderのAB問題を50問解いて体に馴染ませてみた
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
・(appicon generator)[https://appicon.co/]というサイトがアイコン作るのに便利だということ  
・StoryBoardを使うとPhotoshopとかみたいにGUIでTextやImageを簡単に配置出来た  
・SEでビルドしたら、左上がクロッピングされた感じになった ➡︎ AutoLayoutを使えばとりあえず良いと知った  


### クイズアプリを作った
![イメージ 2](https://user-images.githubusercontent.com/18276888/64484552-a04a0b80-d24e-11e9-8cc3-19da51a97163.GIF)  

### おみくじアプリを作った

### お天気アプリを作った

### Todoアプリを作った

## プロのコードレビューを受けた
あるサービスで現場で開発しているiOS開発者にコードレビューを受けた。  
有償でやってもらったので、詳細はこのリポジトリには記述しないが、大まかに
    
・JSONのデコードは自分はSwiftyJSONを使っていたが、JSONDecoderを使うのが一般的ということ  
・プロジェクト全体で使うConstantな値の管理は、Singletonパターンを適用すると良い  
・クロージャ内のselfは[weak self]で弱参照にしないと循環参照になる  
・メインスレッド以外で画面更新を行おうとすると失敗するかクラッシュする  
・自分が書いていたAPIClientモデルの書き方の改善例  
   
などの知見を得ることが出来た。  

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
