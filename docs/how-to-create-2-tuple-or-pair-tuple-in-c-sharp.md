# 如何在 C#中创建 2 元组或对元组？

> 原文:[https://www . geeksforgeeks . org/如何在 c-sharp 中创建 2 元组或对元组/](https://www.geeksforgeeks.org/how-to-create-2-tuple-or-pair-tuple-in-c-sharp/)

在 C#中，2 元组是包含两个元素的[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)，也称为**对**。您可以使用两种不同的方法创建二元组:

*   **[使用元组< T1，T2 > (T1，T2)构造器](#Using Tuple<T1,T2>(T1, T2) Constructor)**
*   **[使用创建方法](#Using the Create method)**

### **使用元组< T1，T2 > (T1，T2)构造器**

**您可以使用元组 <t1 t2="">(T1，T2)构造函数创建 2 元组。它初始化元组<t1>类的一个新实例。但是当你使用这个构造函数创建一个元组时，那么*你必须指定存储在元组中的元素*的类型。</t1></t1>**

****语法:****

```
public Tuple (T1 item1, T2 item2);
```

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**

****示例:****

```
// C# program to create 2-tuple
// using the tuple constructor
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with two elements
        // Using Tuple<P1, P2>(T1, T2) constructor
        Tuple<string, int> My_Tuple = new Tuple<string, int>("GeeksforGeeks", 10);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
    }
}
```

****Output:**

```
Element 1: GeeksforGeeks
Element 2: 10

```** 

### **使用创建方法**

**您也可以在 create 方法的帮助下创建二元组。当你使用这个方法时，那么*就不需要指定存储在元组中的元素的类型*。**

****语法:****

```
public static Tuple<T1,T2> Create<T1, T2> (T1 item1, T2 item2);
```

****类型参数:****

*   ****T1:** 是第一个元组成分的类型。**
*   ****T2:** 是第二元组成分的类型。**

****参数:****

*   ****item1:** 是第一个元组成分的值。**
*   ****item2:** 是第二元组分量的值。**

****返回类型:**该方法返回 2 元组，其值为*项 1* 和*项 2* 。**

****示例:****

```
// C# program to create 2-tuple
// using create method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Creating tuple with two elements
        // Using Create method
        var My_Tuple = Tuple.Create("Geeks", 20);

        Console.WriteLine("Element 1: " + My_Tuple.Item1);
        Console.WriteLine("Element 2: " + My_Tuple.Item2);
    }
}
```

****Output:**

```
Element 1: Geeks
Element 2: 20

```** 

****参考文献:****

*   **[https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.-克托？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.tuple-2.-ctor?view=netframework-4.8)**
*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . tuple . create？view = net framework-4.8 # System _ Tuple _ Create _ _ 2 _ _ 0 _ _ 1 _](https://docs.microsoft.com/en-us/dotnet/api/system.tuple.create?view=netframework-4.8#System_Tuple_Create__2___0___1_)**