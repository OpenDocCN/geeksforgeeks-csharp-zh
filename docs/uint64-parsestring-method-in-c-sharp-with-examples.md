# UInt64。用例子解析 C#中的(字符串)方法

> 原文:[https://www . geesforgeks . org/uint 64-parse string-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-parsestring-method-in-c-sharp-with-examples/)

**UInt64。解析(字符串)方法**用于将数字的字符串表示转换为其等效的 64 位无符号整数。

**语法:**

```cs
public static ulong Parse (string str);
```

这里，*字符串*是包含要转换的数字的字符串。字符串的格式为*【可选空格】【可选符号】数字【可选空格】*。这个符号可以是正的，也可以是负的。但是负号只能和零一起使用，否则会抛出*overowexception*。

**返回值:**是一个 64 位无符号整数，相当于*字符串*中包含的数字。

**异常:**

*   **参数空异常**:如果*字符串*为空。
*   **格式异常**:如果*字符串*格式不正确。
*   **overoverowexception**:如果 *str* 代表小于*T5】MinValueT7】或大于*T9】MaxValueT11】的数字。**

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate
// UInt64.Parse(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // passing different values
        // to the method to check
        checkParse("18446744073709551615");
        checkParse("454654615,784");
        checkParse("-564564564");
        checkParse(" 119846456456  ");
    }

    // Defining checkParse method
    public static void checkParse(string input)
    {

        try {

            // declaring UInt64 variable
            ulong val;

            // getting parsed value
            val = UInt64.Parse(input);
            Console.WriteLine("'{0}' parsed as {1}", input, val);
        }

        catch (OverflowException) {

            Console.WriteLine("Can't Parsed '{0}'", input);
        }

        catch (FormatException) {

            Console.WriteLine("Can't Parsed '{0}'", input);
        }
    }
}
```

**Output:**

```cs
'18446744073709551615' parsed as 18446744073709551615
Can't Parsed '454654615,784'
Can't Parsed '-564564564'
' 119846456456  ' parsed as 119846456456

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// UInt64.Parse(String) Method
// for ArgumentNullException
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // passing null value as a input
            checkParse(null);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining checkparse method
    public static void checkParse(string input)
    {

        // declaring UInt64 variable
        ulong val;

        // getting parsed value
        val = UInt64.Parse(input);
        Console.WriteLine("'{0}' parsed as {1}", input, val);
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 64 . parse？view = net framework-4 . 7 . 2 # System _ uint 64 _ Parse _ System _ String _](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.parse?view=netframework-4.7.2#System_UInt64_Parse_System_String_)