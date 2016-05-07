- http://jibun.atmarkit.co.jp/scenter/ittrain/121_exam_1_q.html

試験時間：14:50 ~ 16:20

## 復習方法
```
$ grep NG toreme.md
```

して間違えたとこ確認

## My Answers
1.  1 foo OK
2.  3 self OK
3.  2 super OK
4.  4 1\n[2, 3] OK
5.  1 ::M::CONST
6.  4 何も出力されない NG(正解：2 Error2)
> rescue節で捕捉できる例外は、指定した例外クラスと、そのクラスのサブクラスです。
この場合、捕捉する例外としてError1を指定していますが、Error1のサブクラスとして定義されたError2の例外がraiseメソッドで発生されているため、Error2の例外を捕捉することができます。

7.  3 OK
8.  4 NULL OK
9.  1 Foo.new.foo OK
10. 2 Foo.foo OK 
11. 3 Foo.foo OK
12. 3 Bar OK
13. 3 private NG
> privateメソッドはレシーバを指定して呼び出すことはできません。
インスタンスメソッドのコンテキストからselfを参照するとそのインスタンスなので、self.[method_name] で大丈夫

14. 1 sum NG(正解：3 inject)
> injectメソッドは引数で初期値を取り、レシーバの要素の先頭から順にブロック内の処理を実行し結果を求めていくメソッドです。
[10] pry(main)> [2, 4, 6].inject(0) { |sum, i| p i}
2
4
6
=> 6

15. 1 5 / 2 OK
16. 1 "A" NG(正解：3 エラーが発生する)
17. 1 sum.call(1,2) OK
18. 1 文字列をIOオブジェクトのように扱うことができる OK
19. 1 {"file1"=>{"name"=>"file1.txt", "data"=>"text"}} OK
20. 3 -d NG
  `ruby -t` は `--disable-FEATURE` の意味
21. 3 attr_accessor OK
22. 1 $match NG(正解：$1)
> 正規表現内の括弧を記述すれば、その位置にマッチした文字列を後から参照することができます。 
>
> 括弧は正規表現内で複数使用することができますが、一致した文字列は括弧が出現した順番に、特殊なローカル変数$1, $2, $3...の順番で代入されます。 
>
> 問題では、括弧を1つ使用しているだけですので、正規表現に一致した文字列を取得する場合、「$1」を使用します。

23. 3 -e OK
24. 2 initialize OK
25. 1 value1 nil OK
26. 1 [:job1, :job2, :job3] OK
27. 3 実行時にエラーになる NG(正解：4 ["b", "b", "b"])
```
[1] pry(main)> Array.new(3, "a").each {|obj| p obj.object_id}
```
28. 2 include Enumerable NG
29. 3 :hello OK
> Object#equal?はオブジェクト同士の同一性判定用のメソッドです。

30. 3 1\n2 OK
31. 4 NG
> 「モジュール名.メソッド名」の形式で呼び出せるメソッドをモジュール関数と呼びます。モジュール関数を定義する場合、メソッドの前に「module_function」を記述します。

32. 4 2行目でエラーが発生する NG(正解：4)
>Rubyには特定のオブジェクトにのみメソッドを定義することができます。これを特異メソッドと呼びます。特異メソッドは問題文のように「オブジェクト.メソッド名」のように定義します。

33. 2 arg="default" OK
34. 2 Fooクラスにはfooメソッドとbarメソッドが定義される OK
35. 2 モジュールはMix-inすることで定数やメソッドなどをクラスに追加することができる OK
36. 1 メソッドのアクセス制限を指定しなかった場合、デフォルトでpublicになる OK
37. 1 OK
38. 2 OK
39. 3 OK
40. NG
> requireはライブラリを読み込むメソッドです。同一のファイルを指定しても2回読み込まれません。 

41. 3 OK
42. 4 OK
> コード１でfooメソッドは未定義化されておりますのでメソッド呼び出し時にエラーになります。 
コード2では、メソッドの未定義化にremove_methodを使用しておりますが、このメソッドはスーパークラスに同名のメソッドがある場合にそれが呼ばれるので、エラーになりません。 

43. NG
> aliasはメソッドに別名をつけるためのキーワードです。 
undefはメソッドを未定義化するためのキーワードです。 
問題文中のコードでは、fooメソッドが定義された後に未定義化されておりますので、fooメソッドの呼び出しでは、superによって問題なく親クラスの同名のメソッドが呼ばれます。

44. 2 ::CONST OK
45. 3 OK
46. 3 inspect OK
> inspectメソッドはpメソッドでオブジェクトそのものを出力した際の文字列表現を指定するメソッドです。

47. 3 NG(正解：4)
>FileTestモジュールはファイルやディレクトリの検査を行う機能をまとめたモジュールです。

48. 2 barbarbar OK
49. 4 barbarbar\nfoofoofoo OK
50. 2 NG
```
[2] pry(main)> Class.ancestors
=> [Class,
 Module,
 Object,
 PP::ObjectMixin,
 Kernel,
 BasicObject]
```

51. 3 false OK
52. 2 OK
53. 1 OK
```
[5] pry(main)> p TCPSocket.ancestors
[TCPSocket, IPSocket, BasicSocket, IO, File::Constants, Enumerable, Object, PP::ObjectMixin, Kernel, BasicObject]
```
54. 4 OK
55. 4 ++i OK
56. 2 OK
57. 2 NG(正解：3 Proc)
> lambdaキーワードはProcオブジェクトを生成するためのキーワードです。

58. 2 NG(正解：3) 
> extendはモジュールで定義したメソッドをクラスメソッドとして追加しますので、メソッドを呼び出す場合は、「Foo.foo」と記述する必要があります。

59. 1 NG(正解：3)
> MarshalモジュールはIOオブジェクトや特異メソッドを持つオブジェクトはシリアライズすることができない

60. 4 Swap OK 

正答：41/60

## Notes
- 2.1 対応の教材を使わないとだめ
- Enumerator::Lazy 遅延評価
- p *[1, 2, 3] のときのアスタリスクの意味(展開するらしい TODO: あとで調べる）
- 5の `::M::CONST`の銭湯の`::`の意味は > トップレベルより定数にアクセスする場合は「::モジュール::定数」という形式でアクセスすることができます。
- オブジェクト指向の「メッセージ」と「レシーバ」の意味がよくわからない
- `inject`の意味をしらない
    - inject: 「注入する, 注射する」
- 凍結されたオブエジェクトの値を変更しようとするとエラー (RuntimeError: can't modify frozen Hash) が発生する
- stringioライブラリってなんだ
- EOY ってなんだ(End Of Yaml?)
    - この問題のdirっていう変数名が何を意図しているのか
- 配列のshift, unshiftがよくわからない
    - unshift(i)で先頭にiを挿入する(shiftは先頭の要素を取り出す）
- `remove_method` と `undef_method` について
- inspectの意味:点検する, 詳しく調べる
- FileTestモジュール？
- Marshal しらん。意味もわからん。

## Links
- http://qiita.com/sengg_m/items/95be0f9b80502218ad8c
