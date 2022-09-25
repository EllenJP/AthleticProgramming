# 問題
# [ABC270A](#ABC270A)
https://atcoder.jp/contests/abc270/tasks/abc270_a
# [ABC270A](#ABC270A)
https://atcoder.jp/contests/abc270/tasks/abc270_a

<br><br><br><br><br><br><br><br><br><br><br>

# 解答
# <a id="ABC270A">ABC270A</a>
```cs
static void Main()
{
    var line = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var decimalToBinaryDigits = Convert.ToString(line[0] | line[1], 2).PadLeft(3, '0');
    Console.WriteLine(Convert.ToInt32(decimalToBinaryDigits, 2));
}
```

# <a id="ABC270B">ABC270B</a>
* wallPos > 0のとき、
    * goalPos < wallPos -> OK
    * goalPos > wallPos -> ハンマー必要
* wallPos < 0のとき、
    * goalPos > wallPos => OK
    * goalPos < wallPos -> ハンマー必要
        * hammerPos < wallPos -> OK
        * wallPos < hammerPos -> NG
よって、wallPos < 0と wallPos > 0の時の条件は-1をかけると同じになることが分かる。
それにより、wallPos > 0のみ考えればよくなる

```cs
static void Main()
{
    var line = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var goalPos = line[0];
    var wallPos = line[1];
    var hammerPos = line[2];
    var ans = -1;
    if (wallPos < 0)
    {
        goalPos *= -1;
        wallPos *= -1;
        hammerPos *= -1;
    }
    if (goalPos < wallPos)
    {
        ans = Math.Abs(goalPos);
    }
    else if (goalPos > wallPos)
    {
        if (hammerPos < wallPos)
        {
            ans = (goalPos - hammerPos) + Math.Abs(hammerPos);
        }
    }
    Console.WriteLine(ans);
}
```
```cs
// wallPos > 0 と wallPos < 0でそれぞれ場合分けした場合、符号反転箇所が多く存在するためミスが多くなる。
static void Main()
{
    var line = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var goalPos = line[0];
    var wallPos = line[1];
    var hammerPos = line[2];
    var ans = -1;
    if (wallPos < 0)
    {
        if (goalPos > wallPos)
        {
            ans = Math.Abs(goalPos);
        }
        else if (goalPos < wallPos)
        {
            if (hammerPos > wallPos)
            {
                ans = Math.Abs(goalPos - hammerPos) + Math.Abs(hammerPos);
            }
        }
    }
    else if (wallPos > 0)
    {
        if (goalPos < wallPos)
        {
            ans = Math.Abs(goalPos);
        }
        else if (goalPos > wallPos)
        {
            if (hammerPos < wallPos)
            {
                ans = (goalPos - hammerPos) + Math.Abs(hammerPos);
            }
        }
    }
    Console.WriteLine(ans);
}
```