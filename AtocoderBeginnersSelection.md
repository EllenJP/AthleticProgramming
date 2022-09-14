# 問題
# [ABC086A](#ABC086A)
https://atcoder.jp/contests/abc086/tasks/abc086_a
# [ABC081A](#ABC081A)
https://atcoder.jp/contests/abc081/tasks/abc081_a
# [ABC081B](#ABC081B)
https://atcoder.jp/contests/abc081/tasks/abc081_b
# [ABC087B](#ABC087B)
https://atcoder.jp/contests/abc087/tasks/abc087_b
# [ABC083B](#ABC083B)
https://atcoder.jp/contests/abc083/tasks/abc083_b
# [ABC088B](#ABC088B)
https://atcoder.jp/contests/abc088/tasks/abc088_b
# [ABC085B](#ABC085B)
https://atcoder.jp/contests/abc085/tasks/abc085_b
# [ABC085C](#ABC085C)
https://atcoder.jp/contests/abc085/tasks/abc085_c
# [ABC049C](#ABC049C)
https://atcoder.jp/contests/abc049/tasks/arc065_a
# [ABC086C](#ABC086C)
https://atcoder.jp/contests/abc086/tasks/arc089_a


<br><br><br><br><br><br><br><br><br><br><br>


# 解答
# <a id="ABC086A">ABC086A</a>
```cs
static void Main()
{
    var input = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    if (IsEven(input[0], input[1]))
        Console.WriteLine("Even");
    else
        Console.WriteLine("Odd");
}

static bool IsEven(int a, int b)
{
    return a * b % 2 == 0;
}
```


# <a id="ABC081A">ABC081A</a>
```cs
static void Main()
{
    var input = Console.ReadLine();
    var ans = input.Where(x => x == '1').Count();
    Console.WriteLine(ans);
}
```

# <a id="ABC081B">ABC081B</a>
```cs
static void Main(string[] args)
{
    var N = int.Parse(Console.ReadLine());
    var A = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var count = 0;

    while (true)
    {
        if (A.Any(x => x % 2 != 0))
            break;
        A = A.Select(x => x /= 2).ToArray();
        count++;
    }
    Console.WriteLine(count);
}
```



# <a id="ABC087B">ABC087B</a>
```cs
static readonly int moneyA = 500;
static readonly int moneyB = 100;
static readonly int moneyC = 50;
static void Main(string[] args)
{
    var A = int.Parse(Console.ReadLine());
    var B = int.Parse(Console.ReadLine());
    var C = int.Parse(Console.ReadLine());
    var X = int.Parse(Console.ReadLine());
    var count = 0;
    for (int a = 0; a <= A; a++)
    {
        for (int b = 0; b <= B; b++)
        {
            for (int c = 0; c <= C; c++)
            {
                if (a * moneyA + b * moneyB + c * moneyC == X)
                    count++;
            }
        }
    }
    Console.WriteLine(count);
}
```


# <a id="ABC083B">ABC083B</a>
```cs
static void Main(string[] args)
{
    var array = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var N = array[0];
    var A = array[1];
    var B = array[2];
    var ans = 0;
    for (int i = 1; i <= N; i++)
    {
        var sum = GetSumDigit(i);
        if (A <= sum && sum <= B)
            ans += i;
    }
    Console.WriteLine(ans);
}
static int GetSumDigit(int x)
{
    var sum = 0;
    while (x > 0)
    {
        sum += x % 10;
        x /= 10;
    }
    return sum;
}
```

```cs
// LINQ使用
static void Main(string[] args)
{
    var array = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    var N = array[0];
    var A = array[1];
    var B = array[2];
    var list = Enumerable.Range(1, N);
    // A <= sum <= Bで絞り込み、合計を出す
    var ans = list.Where(x => CheckSumDigit(x, A, B)).Sum();
    Console.WriteLine(ans);
}
static bool CheckSumDigit(int x, int a, int b)
{
    var sum = 0;
    while (x > 0)
    {
        sum += x % 10;
        x /= 10;
    }
    return a <= sum && sum <= b;
}
```


# <a id="ABC088B">ABC088B</a>
```cs
static void Main()
{
    int N = int.Parse(Console.ReadLine());
    var a = Console.ReadLine().Split(' ').Select(x => int.Parse(x)).ToArray();
    Array.Sort(a);
    Array.Reverse(a);
    var alicePoint = a.Where((_, index) => index % 2 == 0).Sum();
    var bobPoint = a.Where((_, index) => index % 2 != 0).Sum();
    Console.WriteLine(alicePoint - bobPoint);
}
```
# <a id="ABC085B">ABC085B</a>
```cs
```
# <a id="ABC085C">ABC085C</a>
```cs
```
# <a id="ABC049C">ABC049C</a>
```cs
```
# <a id="ABC086C">ABC086C</a>
```cs
```
