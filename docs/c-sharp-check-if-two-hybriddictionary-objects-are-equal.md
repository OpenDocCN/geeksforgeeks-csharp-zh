# C# |检查两个混合字典对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-hybrid dictionary-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-hybriddictionary-objects-are-equal/)

**等于(对象)方法**继承自[对象类](https://www.geeksforgeeks.org/c-object-class/)，用于检查指定的[混合字典](https://www.geeksforgeeks.org/c-hybriddictionary-class/)对象是否等于另一个混合字典对象。

**语法:**

```
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```
// C# code to check whether two
// HybridDictionary objects
// are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key and value in myDict
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "C#");

        // Checking whether myDict is
        // equal to itself or not
        Console.WriteLine(myDict.Equals(myDict));
    }
}
```

**输出:**

```
True

```

**例 2:**

```
// C# code to check whether two
// HybridDictionary objects
// are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict1 = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict1.Add("I", "first");
        myDict1.Add("II", "second");
        myDict1.Add("III", "third");
        myDict1.Add("IV", "fourth");
        myDict1.Add("V", "fifth");

        // Creating a HybridDictionary named myDict2
        HybridDictionary myDict2 = new HybridDictionary();

        myDict2.Add("Australia", "Canberra");
        myDict2.Add("Belgium", "Brussels");
        myDict2.Add("Netherlands", "Amsterdam");
        myDict2.Add("China", "Beijing");
        myDict2.Add("Russia", "Moscow");
        myDict2.Add("India", "New Delhi");

        // Checking whether myDict1 is
        // equal to myDict2 or not
        Console.WriteLine(myDict1.Equals(myDict2));

        // Creating a new HybridDictionary
        HybridDictionary myDict3 = new HybridDictionary();

        // Assigning myDict2 to myDict3
        myDict3 = myDict2;

        // Checking whether myDict3 is
        // equal to myDict2 or not
        Console.WriteLine(myDict3.Equals(myDict2));
    }
}
```

**输出:**

```
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。