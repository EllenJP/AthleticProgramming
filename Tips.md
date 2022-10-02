# 目次
* [2進数の計算](#2進数の計算)


# 2進数の計算<a id="2進数の計算"></a>
* 2進数同士の計算では一度10進数にしてから計算する。
* 2進数を定義するときは0b...とする。
```cs
 100
+011
----
 111
// line[0], [1]は10進数
var line = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray(); 
// 2進数をstring型で返す。左3つ分ゼロ詰め
var decimalToBinaryDigits = Convert.ToString(line[0] + line[1], 2).PadLeft(3, '0');
// string型の2進数を10進数に変換する。計算過程の2進数は一度10進数に直すか、string型で格納しておく。
Console.WriteLine(Convert.ToInt32(decimalToBinaryDigits, 2));
```
