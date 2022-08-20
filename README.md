# 0802

# 記録さぼり + 保存ミスで消えた0729以降の記録を復讐しながら簡易的に再掲載

# ARC031B 埋め立て　2回目

解答遷移  AC

baseまで 17:42  デバック 01:20

備考

➀ 「島がひうとつながりである」か否かの判定を、探索した陸を消して最後に陸が残っているか否かで判定することが可能。

解答例 : https://ebisuke33.hatenablog.com/entry/antbook-arc031b


# 233A 10 yen Stamp

備考

➀ XをYで割った解の小数切り上げ

(X+Y-1)//Y

イメージ的にはX//Yをbaseに、XがYで割り切れる時以外は、+Yの部分が効いて切り上げられる。

割り切れる場合は-1の部分が効いて、切り上げが起こらないようになる。

➁ Xが既にYを上回っている場合

この場合に((X+Y)+10-1)//10 をすると負値になるので条件処理するか、max(0,)とする



# アルゴ式 グラフアルゴリズム

# 1-2 フォロー

備考 

なし



# 1-3 人気者の友達 2回目

解答遷移 AC

baseまで 08:08  デバック&提出 04:52  計 13:00

備考

➀ * 復習 mapはイテレータ

A=[1,2]のとき

a,b=A , a,b=map(int,A)  と要素にアクセスすれば違いはないがa=Aとすればリストが返ることと違ってイテレータは返らない

➁ 復習時と初見時の方針の違い　（情報の分割)

復習時

ABを入力から得た友達リストとしてA[n]に[nの友達の数(len(AB[n]) , -n , AB[n]]を格納しソートすることで友達の数が多い順でかつindex番号が小さい順に並べ替えることができる。そして最後にsorted(A)[0][-1]をソートすればよい。

初見時

入力からで友達リストを作成すると同時に、友達の多さリストを作成。多さリストの最大値のindex番号こそ、友達が最も多くindex番号が小さいもののindex番号になるので友達リストからそのものの友達を求めればよい。


確実に初見時のほうがスマート。ループ処理1回で解決している。全ての情報をはらんだリストを再構築する復習時のほうが情報をコンパクトにまとめられる点は優れているが、友達の多さは多い順、index番号は若い順で異なるためindex番号を-1倍処理する必要があることや、そもそもどんな情報を格納すべきか難しい部分があるため自分では実装に時間がかかってしまう。



# 1-4 友達の友達 2回目

解答遷移 AC

備考

➀ リストの要素検索

a (not) in A としてAの要素にaがあるかの処理は　O(n) である。よって制約次第で使えなくなる可能性が高い。setであればO(1)らしいのでこちらを使用するようにする。

![image](https://user-images.githubusercontent.com/109026838/182563153-57676d80-383b-4188-a3d3-7d2f9bf4e5ef.png)

*  2-2後 追記

リストをセットに変換して要素検索するのと、セットを直接検索するのとでは計算時間が異なる(0801_0806 tttt.py参照)

そのため検索したい場合にはあらかじめ空のset()を作っておき、こちらにも値を格納する処理がTLEしないためにより良い。




# 2-1 箱の中の箱　2回目

解答遷移 AC

問題把握 01:43  発想 01:42  base & デバック 05:05  計 08:31


備考

➀ 根からの探索

特定の頂点(箱)Xの深さを調べるなら、根からでたらめにたどっていくよりも直接その頂点から根に向かった方が効率的

➁ dp的解放

「ある頂点(箱)における根からの深さは、その親の頂点の深さ+1 」 である性質を利用すればすべての頂点の深さを求めることができる。


# 2-2 行きがけ順　2回目

解答遷移 RE(TLE)  AC 

問題把握 00:32 　発想 00:01  base 17:13  計 17:46

備考

なし


# 0804

# 2-3  頂点の深さ　2回目

備考

➀ 探索の方向

今回は全ての頂点の根からの深さを求めることになるので、特定の頂点から出発するほうが良いと思われる。この場合自分の子の深さを+1して、その子を根とした部分木に対して同じ処理をすればよい。

逆に頂点からスタートするとその親の深さが分かっていな可能性があり、その時用の別の処理が必要になり煩雑化する。


# 2-4 木の高さ　2回目

解答遷移 AC

問題把握 00:27  発想 00:00  base 04:28  デバック 00:53  計 05:49

備考

2-3と同じ処理が9割9分を占めるので復習必要ない



# 2-5 子孫の個数   諦めてみ正解状態(解説等見てない)

解答遷移　AC

問題把握 & 発想 13:01  base 11:23  デバック&提出  14:53  計 39:18

備考

➀　行きがけ、帰りがけ

木構造において部分木を探索する前に処理を施す場合を行きがけ、部分木の処理が完了してから処理を施す場合を帰りがけという。

頂点の根からの深さはその親の深さがわかっていれば+1することで求められるので、ある頂点の深さは根方向から順に、つまり行きがけ順に求められる。逆にある頂点の子孫の数などを求めたい場合などは、子孫に対する処理が完了していないとわからないので葉方向、つまり帰りがけ順に求めることができる。

codeでは dfsを再帰する前に処理するか後に処理するかだけの違いである。




# 230A AtCoder Quiz 3

備考

➀ 初見で一瞬でできた記憶があるため再回答せず。特に記述もなし




# 229A First Grid

備考

➀ 条件を満たすパターンが限られているので、ループを回すよりも直接入力が条件を満たすか判定するほうが楽なパターン



# 228A  Mnay Oranges　2回目

解答遷移 AC

問題把握 & 発想 00:00  base 05:08  デバッグ&提出 00:31  計  10:51

備考

➀　探索対象は何？

重さがWという条件から、みかんの重さを動かし合計がWになるような状態を見つけたくなる。例えばW=1500でみかんの最小値が400 最大値が800の場合、800のみかんを選び残りは700で範囲内にあるので最小値は2個という方針を取りたくなる。しかしW=1700の場合では、800のみかんを２つ選んでも残りの重さを補える重さのみかんを選ぶことはできない。そのため今度は800のみかんを1つ選び次に799のみかんを、、、とはてしない処理を行うことになる。

このように自然に思い付いた方針がだめなら視点を変えてみよう。例えば動かす対象を重さからみかんの個数に変えることでこの問題は解決できる。A * i<= W <= B * i ・・ ➀　が成り立つなら、重さの組み合わせこそわからないが、i個選べばちょうどWとなるようにみかんを選ぶことは判別できる。これをW < A * j になるまで繰り返し一番最初に➀を満たしたiが最小値となり、一番最後に➀を満たしたiが最大値となる。



# ☆ 257C Robot Takahashi  2回目

解答遷移 TLE 諦め

備考

➀　listのsliceの計算量

スライスはcopyしてるらしく、要素の長さkに依存するO(k)になるらしい。そのため大人と子供の境界を探索したうえで、大人リストと子供リストを作ると計算量は O((10^5)^2)になりTLEしたと考えられる。


➁ sliceを使わない境界前方の0の数と1の数の数え上げ

1,境界の移動で生じる±を逐次計算

2,累積和

3,2部探索


③ Wが重複している場合の境界線の処理(工夫ver)
  
10の順では、|10 の境界線の位置の状態で一致数がXだった場合 1|0 ではX-1となり、10|でXに戻る。一方、01の順では 0|1でX+1となり、01|でXに戻る。

つまり01野場合では重複時に存在しえない境界線が一致数の最大値を不当に更新するが10野場合には更新されずに済むので、Wをの昇順をもとにsortしたうえで、10の順(降順)にSをsortしさえすれば重複を考慮しない実装が可能になる


④ 重複を考慮した逐次処理

境界の左側に含まれる0の数と1の数を境界を移動させるごとに数え上げその和の最大値を求める処理、境界の移動による正解判定数の現在値と最大値の比較。どちらの方針であっても体重重複の有無に関わらず、境界の左側に移動した値が0か1かで値を変化させる処理を行う。重複がある際に特別になることはは最大値の更新のみである。つまり重複がある場合を条件処理して特別な処理を行う必要はなく、通常の処理を行った後、更新を行う前に重複があるかを判定して、あるならcontinueで判定処理を回避するだけ、ただそれだけである。



# 0806

# 236C Route Map
 
解答遷移 AC

問題把握 02:41  発想 01:51  base 05:04  デバック&提出 00:26  計 10:04

備考

➀ set検索がO(1)であることを利用すればよいだけ

➁　それ以外の方針

1, n番目の駅は止まる駅か否か判定　→ 止まるなら止まる駅リストのindex番号を後ろにずらして次の止まる駅を検索可能にする

2, 止まる駅リストの駅に止まったらそれをリストから削除して、同じindex番号で判定し続ける。

→ TLEしないようにpop(-1)するしかないので逆順処理。



# 256C Filling 3x3 array　2回目

解答遷移 WA* 5 AC

問題把握 & 発想 03:22   base 05:39  提出 06:16  計 15:17 + 5* 05:00


備考

➀  上4マスが定まれば他のマスが一意に決まることを利用して導出。それら全てが>0以上であることに加えて間接的に求めた値で計算した最後のマス計算時に使用していない条件を満たせばカウンターを+1する処理をするだけである。

初見時の自由な発想はすばらしいが、3回ループそれぞれでproduct演算する計算量が不安。条件処理で計算量を落す方が賢い。



# 228A On and Off 

備考

➀　初見でそこまで苦労せず解けた記憶があるので解きなおしなし


# 254C kswap  2回目

解答遷移  AC

問題把握&発想 13:31    base 14:34     デバック&提出 03:29  


備考

➀ 解答状況

1, sortedの各要素を入れ替えて元のリストに戻せるか　→  計算量をクリアする方針を熟考  →  移動可能なリストを作成し、そこにsortedの要素があればYesな処理を行うことにした(この時点ではどの様なコードにするか割と曖昧なまま走った)

2, コードを作成していく都度、よりよい発想が出てくるようになった。移動可能範囲は余りで分類できるし、重複もcollection.Counterで処理できることが明確化して完成


➁ 入れ替え可能範囲限定でsortedして、それが元のリストのsortedだったらYES

初見時の解法。K * N//K * N//K で計算量危なそうだなと思ったが、こっちの方が速くて？

 

# 0807

# 227A  Last Card 

備考

➀ 元のindex番号との連携

余りで分類したい + 配った枚数-1個番号を進めるため ( (A-1) + (K-1) ) % Nによってindex番号0 始まりのリストにおいて最後にカードが配られた人間が分かる。これをもとのリストのindex番号に戻すために +1 すると完成


# 198B Palindrome with leading zeros 2回目

解答遷移 AC

問題把握&発想 02:54   base 02:17  デバック&提出  05:27  計 10:39

備考

➀　桁数がmaxでも10なので絶対TLEは起きないだろうが、0の挿入位置が最後のほうが楽なので逆順のリストの末尾に0を加えていき、これを逆順したリストと同じになれば回文と判定する処理にした。なお0を加える回数はめんどくさいのでNの長さによらず10回とした。

➁ リスト == リスト　

全ての要素が同じならTrueになる。オブジェクトが否かは関係ない。もしこの問題で異常が発生したならそれはおそらくリストの要素とappendで加えた0の型が異なるというだけであると思われる。



# 251C Poem Online Judge 2回目

解答遷移 AC

問題把握 & 発想 03:00  base 02:43 デバック & 提出 02:52  計08:36

備考

なし




# ☆ Slot Strategy  2回目

解答遷移 WA TLE TLE RE AC

問題把握 04:33  発想 02:29  base 04:17  デバック&提出 1:07:17  計 1:18:37 + 20:00


備考

➀ whileループのカウンター処理忘れ

カウンター自体は作成できるが、カウンターを更新する処理を行うのを忘れてしまうことが多い。必ずつける

➁ 0-9のどれを揃えるかで全探索、同じ数字が同じ列になければ一番最後の列秒でそろえることが可能。もし同じ列にあれば、繰り返す回数は頻度の最大値、最後の位置はその列である、と考えていたのだが頻度の最大値が複数存在する場合に最後の位置はその中で最も後ろの列になる。数字の列の場所はcollections.Counterで管理し、most_commonで最頻値にアクセスする。実装にてまどったが、最頻値が重複する場合の処理は素直にmost_commonを前から順にアクセスして後ろの出現回数と同じなら列の番号を比較する処理を実行した。


③ 初見案

0-9のどれを揃えるか全探索する場合、各列ごとにいくつあるか知りたくなる　→ 各列の0-9ごとの頻度を格納したカウンターを作りたい　→ しかしcollection.Counterは存在しない値が格納されないので列ごとに一気に取り出すのは適さない。そこでリストcolumn_countを作成し、0次元方向に各列の情報を、一元方向に0-9のその列における頻度を格納した。それをzip処理することである数字の列ごとの頻度をとりだすことが可能になる。あとはその最大値-1を繰り返し回数、最大値のindexを止まる場所として取り出しある数字を揃える最小時間を求めることができるようになる。



# 226A Round decimals  2回目

解答遷移 AC

計 05:07


備考

➀ math.floor math.ceil

これらは小数の切り捨て、切り上げである。

➁ round(X,n) + 0.0000000000000002

偶数丸めの四捨五入。n桁目(小数第一位を0として、小数点方向を負で進み、末端方向を+で進む)が0-4なら切り捨て、6-9なら切り上げる。

しかし通常の四捨五入と異なり、5のときに結果を偶数に丸めこむ。なぜか+0.000005のように捨てられるくらい適当な数を足すことで、偶数の回避回避や深い小数点の四捨五入もできるようになるので必ず付け加えよう。




# 0808

# 249C Just K　2回目

解答遷移 WA AC　

問題把握 & 発想 07:59  base-提出 07:31  提出 15:31 + 05:00

備考

➀ N <= 15 と適切な数を選ぶ処理の必要性からbit探索をかんがえた。対象の文字列を全て一つのリストに格納してcounterでカウント

➁ * 復習 bit全探索

for i in range(2^N) for j in range(N) とするか、どれを選ぶかのbool値リストで for i  proudt((0,1),repeat=N) for j in range(N)とする

③ Counterへの要素の追加

1, 予めすべての要素を格納したリスト X を作成してCounter(X)

2, 空のCounter Z を用意し、uppdateで追加 Z.uppdate(S[j]) 

![image](https://user-images.githubusercontent.com/109026838/183347963-8fe5e95d-8594-479d-a399-c7c18f4bc0fa.png)

辞書型のupdateに似ているが、あちらは(key,value)のセットで追加するのに対し、こちらはkeyのみを要素にしたiterableを要求する。valueは出現回数から自動で出力される。

3 , 空のCounter Z を用意し、素直にZ[key]+=1

処理時間は 1 < 2 <<3 である。要素数の数だけforループを回す必要のある3が遅いのは当然だが、updateも早くないのでまとめてCOunterに格納しよう



# 246C Coupon 2回目

解答遷移 AC

問題把握 05:37  base 08:09  デバック&提出 01:03　計 14:49

備考

➀ クーポンを使う枚数で全探索すると制約に引っ掛かりそうだと感じた。するとそもそも値段//Xがクーポンを有効に使える枚数だし、値段%Xが残った値段であることに気づいたのでこれを利用した。


➁ 再起関数の挙動

再帰関数の処理の途中でreturnしても、最後の処理の返り値に置き換えられてしまう。そのためなにか保存したい場合は変数やリストを生成して保存するのがよいだろう。




# 242C 1111gal password 2回目

解答遷移 AC

問題把握 04:48  base 04:59  デバック 08:33  計 18:21

備考

➀ 巨大数は扱うのに時間が係るので随時余りを格納すること

➁ ループ数的にも問題なさそうだがなぜかpythonではTLEになるので、腹立たしいがpypyで出した。



# 055B Training Camp

備考

➀ 242Cと同様、余りを利用すること。再解答はしていない




# 238C digitnum

解答遷移　Ac

問題把握 05:38  base-提出 11:05  計 16:43

備考

➀ Nが一桁の時だけ例外処理したが、10^0=1 10^1=10と同一に扱えるのでそんな必要はなかった。




# 241C Connect6  2回目

解答遷移 AC

問題把握 06:21  base-提出 28:09  計 34:31

備考

➀ 解答思考

コード作成前

マスを探索するからdfs? でも白マスの塗りつぶしを探索すると1000C2通りの塗りつぶし探索が加わるのでこれは無理そう。

探索中に白マスの数カウントして3以上になったら処理を行わなくすればいいか

コード作成中

探索は一方向しか進まないから再起関数使わずにforループで良いと気づいた。白マスの数とマスの範囲で条件処理して黒マスが連続して6つ並べばflagをTrueに変え、それを判断材料にansを出力する処理を実装した。


➁ 移動方向

コード作成時は気が付かなかったが、探索する移動方向は8方向でなくてよい。例えば東方向(1,0)を探索するなら、西方向(-1,0)はいらない。なぜなら西方向は既に東方向探索で検出されているからである。この考えで探索方向は8から4に落とすことが可能。


③ 別解

6つのマスをとりだして、黒が4マス以上あればYes判定

白を数えないで済む点がすぐれているが、例えば以下のような例で正しくNoを出力する処理を実装する必要がある。

![image](https://user-images.githubusercontent.com/109026838/183443233-0291d24c-debb-4849-9036-f249b833d7c7.png)


④ 別解2

これまでの解法は 方向 × マス数 × 連続マス数 の24 × N^2 の計算量であるがこれは連続マス数が6であるがゆえに許される。もし連続マス数が膨大になればTLEしてしまう。この状況でも処理可能な方針のひとつに、累積和の考えでマスの数を数えるというものが考えられる。

進行方向ごとに黒マスの数を累積していった値を格納し、始点を探索して終点との価の差に注目する方法である。注意する点としては、始点が黒マスか白マスかで連続を成立させる差の値が異なることがある。


# 以上再解答終わり

=======================================================================================================

# 以下再び編集データ消滅

# 8/9 

# 247C 1 2 3 1 2 3

解答遷移 AC

備考

➀ リストの結合は新たなリストを作成する



# 245C Choose Elements

解答遷移 WA WA AC

備考

➀ 探索方向に注意

普段は同じ行の要素を全て探索し終えた後、いつ下の行に探索を映る処理を行っているが、前の列の値を参照するdpをしたいのであれば、同じ列のすべての要素の探索を終えずに次の列に移ってはいけない。よって普段とは異なる探索をする点に気を付けたい。



# 243C Collision2

解答遷移 AC

備考

➀ 思考

y軸の値で分類して、2点が条件を満たすかという処理は絶対にTLEするので不可能。

[y軸の値, x軸の値,進行方向]を格納したリストを作成しsortして、前から順に探索しx軸の値が同じ値なら進行方向で判定する処理ならば十分高速だと考え作成




# ☆ 233C Product

解答遷移 方針がわからず諦め

備考

➀　条件の見方と絞り込み

１つの袋に入っているボールの数がそれぞれ10^5以下ではない。すべての総和が10^5以下である。よって全探索可能。

また、1つの袋には少なくとも2つボールが入っているので、2^10 * 2^6 < 10^5 < 2^17 より最大でも袋は16個しかないのがわかる。

➁ 再起関数

dfsで扱っていた再帰関数とは言ってしまえば何重ものforループ処理である。この問題のように2つ以上の袋のボールの組み合わせを全探索したいときに有効である。

また再帰関数において保存したい値は引





# 北海道旅行により少し飛ぶ


# 08/19

# ☆ 225C_Calendar Validator

解答遷移 WA WA 諦め

問題把握 05:21  27分で降参


備考

➀ WA の理由

Bの全要素をB[0][0]で引いたBを作成、Bの要素すべてが行index * 7 + 列index になっているかを判定する処理で十分だと思っていたが、例えば 7 8 9 と一行に並ぶことを許してしまう点でこの処理では不十分であった。

よって、B[0][0]とMの関係に制限を設ける必要がある。具体的には、B[0][0]-1 (余りを0始まりにするための-1調整) とMの和が7より大きければ、例のような同じ行に存在し得ない要素が存在している状況であると判断するような処理をはじめに追加した。これによってACすることができるようになった。



➁ なぜコーナーケースを発見し損ねたか？

メインの処理を精査するとき、処理の内容など考慮しないで主観のみで適切なBを与えて検討を行った。これがよくない。例えば、B[0][0]を引く処理によって要素の情報が抜け落ちてしまうところに注目すれば例のような状況を考慮し損ねていることに気づけたかもしれない。処理を中心にした検討を心掛けたい。



③ u2dayoの解説が意味不明。問題が変わった？


# ☆ 223C Doukasen
 
解答遷移　TLE AC　

計 1:31:02 + 05:00


備考

➀ 方針

何本目の導火線でぶつかるのかを導火線を全探索して求め、その導火線でぶつかる点をXとした方程式をたてればよいと判断。

ぶつかる導火線は、左からその導火線を燃やし尽す時間の合計と、右からその導火線を燃やし尽くすまでの時間の合計の差が初めて正になるものと解釈した。したがって、左からの導火線を燃やし尽す時間の累積和と右からの累積和を作成しそれを前から順に探索して条件を満たすときに方程式を解く処理を実装した。

➁　TLE

逆順の累積和を求める際にループ内でソートしてしまったためにTLEしてしまった。メインの処理の速度が高速なことしか確認しなかったために生じた。

③　模範解答

ぶつかるまでの時間は、導火線全体を燃やし尽す時間の半分なことに注目する。

導線を全探索して、その導線までのすべてを燃やし尽す時間とぶつかる時間を比較。ぶつかる時間のほうが大きければその導線の長さを累積し、そうでなければその手前の導線まで燃やし尽す時間とぶつかる時間の残り時間分で燃える長さを累積して終了する処理を行うことで解答可能


④ なぜくそ時間がかかったのか

222C 217B 実装終わりに記述。旅行で間が空いたことで集中力が低下していること、メガネがなく目が疲労している状態であることも少しは影響しているだろうが、diffが茶に近いと解答時間が急増する事実は実力がその程度であることを表していると思われる。さらに222Cが単純な変数のケアレスミスであることと違ってこの問題では純粋に実装にてこずった。もしかすると方程式の実装が苦手なのかもしれない。




# 222C Swiss-System Tournament

解答遷移 WA AC

計 1:02:58 + 05:00

備考

➀ WAのデバック

WAの数的にコーナーケースではなく処理自体に誤りがあるのだと思ったが、いくら考えても間違っているとは思えなかった。仕方ないのでとりあえずメイン処理のじゃんけんする2人のindex番号を取得する処理や、battle関数を簡潔化して解決しないかなと試すとACして余計に困惑した。これらを比較するとbattle関数内で扱う変数が誤っているだけだった。このようなケースは文字検索で誤りを確認できるため次回から活用したい。


➁ 二重リストsort

得点が同じならindex番号の若い順に並べるような処理は二重リスト[得点,-index番号] を降順にsortすることで実現していた。しかし[-得点,index]を昇順sortすることでも実現可能である。


* 補足 x^y

xが奇数の場合x-yを返し、偶数ならx+yを返す？

今回battle関数で誤ってi-1とするところをi^1としてしまったが、iが奇数のために偶然正しい処理ができたのだろうか。^の機能を調べてもよくわからなかった


# 217C Inverse of Permutation 

解答遷移 AC

問題把握 発想  03:30  base&デバック提出 03:52  計 07:22


備考

なし



# 0820

# ☆ Happy New Year!　コードは必要ないかも、解放を確認する復習が必用

問題把握 & 発想 07:52  base - 諦めb 27:09  計 35:02

備考

➀ 思考

n桁の2,0からなる正整数が2^(n-1)個存在することに注目。nを0から始めてKから2^nを引いていきこれをremとして、初めてremが2^nを下回るところまで繰り返す処理を行う。その後(0,2)からn個取り出す処理をitertools.productで行いrem-1番目のものを"2"に足したものを出力する処理で良いなと思った。

しかし10^18であるKに対してこの処理を行う場合 nが60近いになるためbit演算の処理できる範囲を超えてしまっているためにTLEとなる。その後別案が浮かばなかっため降参した


➁模範解答

求めるべき数は2進数の数値においてK番目に小さい数の1の部分を2に変換したものと解釈できる。

bin(K)[2:] or f"{K:b}"で求めるべき2進数を文字列で出力し、replace("1","2")で文字列内の1を2に変換するか、int型に変換して2倍するかすればよい。




* 復習

mapはイテレータ。取り出す場合はリスト化が必用。


* 補足 itertools.product(X,repeat=0)

range(0)などとは異なり、空の返り値を返す。この仕様によって、K=1の処理を偶然適切に行えた




# 228C Final Day

解答遷移 AC

問題把握 発想 03:31  base 04:45  デバック&提出 01:39  計 09:56

備考

なし





# 235C The Kth Time Query 

解答遷移 AC

問題把握 02:05 発想 01:36  base 07:45  デバック&提出 01:55  計 13:22

備考

➀ collections.defaultdict(関数)

Aに出現する数をキーとして、それらすべての出現場所を格納したリストをvalueにした辞書を作成すれば、O(1)の処理で済むが、collections.Counterとは異なり辞書は存在しないキーにアクセスできないため、条件分岐で初めてアクセスする場合にリストを与えてから、それ以降にappendする必要があった。

collections.defaultdictは、valueの型を与えた関数型で初期化(統一？)し、存在しないキーにアクセスしても空のそれに対して操作可能な辞書のようなdefaultdictを作成することができる。

たとえば出現場所を格納したリストをvalueにした辞書を作りたいのであれば、itertools.defaultdict(list)として、キーの存在の有無にかかわらず.append()すればよい


































