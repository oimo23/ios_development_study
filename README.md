# ios開発/Swift に関して勉強した記録
Swift, iOS開発未経験の状態から何を勉強したかとそのコードについて全てこのリポジトリに記録してみました。  
    
なるべく自分の言葉そのままでメモしたかったので、以下からは丁寧語や敬語は使わないこととします。

------------------


## 1.まず基礎的な文法を勉強
手軽にSwiftを動かせる環境として、Playgroundも良かったが共有も簡単な [Repl.it](https://repl.it/) というオンライン上で使えるエディタのWebサービスを活用した

### 目的別にググって出てくる記事を見ながらrepl.it上で手を動かして確認した

下記に文法名とリンク先に実際書いて勉強したコード  

-変数/定数宣言  
https://repl.it/@oimo23/Bian-Shu-Ding-Shu  

-配列  
https://repl.it/@oimo23/Pei-Lie    

-関数定義  
https://repl.it/@oimo23/Guan-Shu-Ding-Yi  

-ループの書き方  
https://repl.it/@oimo23/Zao-riFan-si
 
-Math系  
https://repl.it/@oimo23/MathXi    

-map,reduce,filter  
https://repl.it/@oimo23/map-reduce-filter

-sort  
https://repl.it/@oimo23/sototoreverse

-struct  
https://repl.it/@oimo23/Structtoha

-optional型について  
https://repl.it/@oimo23/Optionaltoha

## 分からないと思った所と自分なりの答え
-Optional型  
Swift特有でとっつき辛かった  
nil (null) が入っているかもしれない型のこと  
Swiftではnilはちゃんと扱わないとアプリが落ちるようだ  
String? なら、Stringかnilを許容する  

StringとString?は型としては完全に別のもの  
Optional型から値を取り出すときにはUnwrapという作業が必要になる  

-強参照、弱参照  
よく分からない  
強参照だとメモリが解放されず無駄遣いになるという事があるのでなるべく弱参照が良いということだけは何となく分かった  

-delegateって結局なに？  
委譲するとかいう意味らしい  
イベントが発生したときに、誰に処理を任せるかという指定？？  
まだいまいちシックリ来ていない  

- protocolとは？  
classやstructがどんな関数や変数持ってるか指定するもの？
普通の変数に対して型が指定されるのに対して、classやstructにはprotocolを指定してやるという事か？

-lazyってなに？  
参照されるとき初めて初期値が設定される  
メモリの節約のため？ 画像で言うところ必要な時まで読みこまない lazy load 的な発想から lazy って名前なのか？

-guardってなに？  
よく分からなかったが、
Optional型の安全なunwrapの時に使うものと理解した  

-画面サイズによるズレはどうする？  
AutoLayout (Constraint)を使う  
グラフィカルに絶対位置じゃなくて相対位置を指定できる  
複雑なものをつくろうとすると、AutoLayoutのデメリットもあるらしいがまだよく分からない  
UIstackViewというものもあるみたいだ  

-型じゃなくて、変数の後ろに?や!が付いてるのは何？  
!はOptionalの強制アンラップ
?はなに...?

-配列のあとに()付いているのは何？  
var list = [Question]()  
分からない  

-cocoapodsってなに？  
パッケージ管理をしてくれる
多分npmみたいなもの  

pod init でファイルが出来て、そこに必要なパッケージの名前を書いて cocoapod install すると入れてくれる  
    
ファイル内で「import ○○」と書くと使えるようになる

-関数の引数のところに付いているアンダースコア(_)は何？  
_ をつけると引数名を省略出来るらしい
func numberThreeTimes(_ num: Int) -> Int {
  return num * 3
}

numberThreeTimes(2) // これで良くなる

-xcodeproj xcworkspaceの違い  
まだよく分かっていない

-classの前の final ってなに？  
finalをつけるとそのクラスは継承されないことが保証されるらしい  

## 2.AtcoderのAB問題を50問解いて体に馴染ませてみた
プログラミング言語の文法を体に身に付かせるのはAtCoderのAB問題をやるのが一番良いと思った経験からやってみた
   
[そのリポジトリ](https://github.com/oimo23/Atcoder_Swift)

-得られたこと  
1で学んだことが体に馴染んだ  

-新たに気付いたこと  
0除算をするとバグる  
配列に対するmax()など　返り値がoptionalなやつがあるので注意しないといけない    
optionalの安全なunwrapは guard let unwrapped = mayOptional else { return }    でやる？


## Hello Worldアプリを作った
![イメージ](https://user-images.githubusercontent.com/18276888/64484545-9de7b180-d24e-11e9-946e-c4e23be1a321.GIF)  
本当にテキストと画像が出るだけ  

- 得た知識
・アイコンの設定の仕方  
・アイコンは解像度別に何種類か用意してあげないといけないこと  
・(appicon generator)[https://appicon.co/]というサイトがアイコン作るのに便利だということ  
・StoryBoardを使うとPhotoshopとかみたいにGUIでTextやImageを簡単に配置出来た  
・SEでビルドしたら、左上がクロッピングされた感じになった →
 AutoLayoutをとりあえず良いと知った  


## クイズアプリを作った
![イメージ 2](https://user-images.githubusercontent.com/18276888/64484552-a04a0b80-d24e-11e9-8cc3-19da51a97163.GIF)  


## これから頑張りたいこと
- RxSwift

- プロトコル指向やSwiftっぽい書き方ってなんなのか

- SwiftUI

- UI / UX / DX について
