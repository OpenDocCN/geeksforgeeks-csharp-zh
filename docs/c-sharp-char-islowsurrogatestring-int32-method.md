# C# | Char。IsLowSurrogate(字符串，Int32)方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-islowasuretestring-int 32-method/](https://www.geeksforgeeks.org/c-sharp-char-islowsurrogatestring-int32-method/)

此方法用于指示字符串中指定位置的 Char 对象是否为低代理。

**语法:**

```
public static bool IsLowSurrogate (string s, int index);
```

**参数:**

> **s** :是一根弦。
> 
> **索引**:是 *s* 中要评价的人物位置。

**返回值:**如果 *s* 参数中指定字符的数值在`U+DC00` 到`U+DFFF`之间，则该方法返回*真*，否则返回*假*。

**异常:**

*   **参数空异常:**如果 *s* 为空。
*   **argumentout of range exception:**如果*指数*不在*的*之内。

以下程序说明了**字符的使用。IsLowSurrogate(字符串，Int32)方法**:

**例 1:**

```
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a', 
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                + "Surrogate value at index {1} ",  s, i);

        else
            Console.WriteLine("String '{0}' does't contain any Low"
                           + "Surrogate value at index {1}", s, i);

    }
}
```

**Output:**

```
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2

```

**示例 2:** 适用于*参数异常*

```
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);

            Console.WriteLine("");
            Console.WriteLine("s is null");
            check(null, 4);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                  + "Surrogate value at index {1} ",s, i);

        else
            Console.WriteLine("String '{0}' does't contain any Low"
                            + "Surrogate value at index {1}",s, i);

    }
}
```

**Output:**

```
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2 

s is null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为*argumentout of range exception*

```
// C# program to demonstrate
// Char.IsLowSurrogate(String,
// Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // calling check() Method
            check("1234", 3);
            check("Tsunami", 3);
            check("psyc0lo", 4);

            // declaring and initializing string s1
            string s1 = new String(new char[] {'a',
                        '\uD800', '\uDC00', 'z' });
            check(s1, 2);

            Console.WriteLine("");
            Console.WriteLine("index is less than zero");
            check("null", -4);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining check() method
    public static void check(string s, int i)
    {
        // checking condition
        // using IsLowSurrogate() Method
        bool val = Char.IsLowSurrogate(s, i);

        // checking
        if (val)
            Console.WriteLine("String '{0}' contains Low "
                  + "Surrogate value at index {1} ",s, i);

        else
            Console.WriteLine("String '{0}' does't contain any Low"
                            + "Surrogate value at index {1}",s, i);

    }
}
```

**Output:**

```
String '1234' does't contain any LowSurrogate value at index 3
String 'Tsunami' does't contain any LowSurrogate value at index 3
String 'psyc0lo' does't contain any LowSurrogate value at index 4
String 'að??z' contains Low Surrogate value at index 2 

index is less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . char . islowsurrogate？view = net framework-4 . 7 . 2 # System _ Char _ IsLowSurrogate _ System _ String _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.char.islowsurrogate?view=netframework-4.7.2#System_Char_IsLowSurrogate_System_String_System_Int32_)