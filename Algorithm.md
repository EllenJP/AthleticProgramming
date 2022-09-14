# 単純選択法（）


# 単純交換法（バブルソート）
```cs
static void Main(string[] args)
{
    var array = new int[]{ 5, 3, 2, 1, 4 };
    for (int i = 0; i < array.Length; i++)
    {
        for (int k = array.Length - 1; k > i; k--)
        {
            if (array[k - 1] > array[k])
            {
                var tmp = array[k - 1];
                array[k - 1] = array[k];
                array[k] = tmp;
            }
        }
    }
    foreach (var item in array)
    {
        Console.WriteLine(item);
    }
}
```


