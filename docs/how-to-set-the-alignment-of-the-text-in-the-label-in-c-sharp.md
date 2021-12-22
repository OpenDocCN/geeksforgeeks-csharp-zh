# 如何在 C#中设置标签中文本的对齐方式？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 标签中文本的对齐方式/](https://www.geeksforgeeks.org/how-to-set-the-alignment-of-the-text-in-the-label-in-c-sharp/)

在 Windows 窗体中，Label 控件用于在窗体上显示文本，它不参与用户输入或鼠标或键盘事件。您可以使用窗口表单中的**文本对齐属性**设置标签控件中文本的对齐方式。您可以使用两种不同的方法设置此属性:

**1。设计时:**使用以下步骤设置标签控件的 TextAlign 属性是最简单的方法:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/f1d477c51402b2df11d7ed28eee617fe.png)
*   **步骤 2:** 从工具箱中拖动标签控件，并将其放到窗口窗体上。您可以根据需要在 windows 窗体上的任何位置放置一个 Label 控件。
    T3】
*   **Step 3:** After drag and drop you will go to the properties of the Label control to set the TextAlign property of the Label.
    ![](img/6a90ef39f750dc2d88c985d7796b84e9.png)

    **输出:**

    ![](img/0a1587bdcfd5362fd3915672b9eb85dd.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以借助给定的语法以编程方式设置标签控件中文本的对齐方式:

```cs
public virtual System.Drawing.ContentAlignment TextAlign { get; set; }
```

这里，内容对齐指定文本的对齐方式。如果分配给该属性的值不属于*内容对齐*值，它将引发*InvalidEnumArgumentException*。以下步骤用于设置标签的文本对齐属性:

*   **步骤 1:** 使用标签类提供的标签()构造函数创建标签。

    ```cs
    // Creating label using Label class
    Label mylab = new Label();

    ```

*   **步骤 2:** 创建标签后，设置标签类提供的标签的 TextAlign 属性。

    ```cs
    // Set TextAlign property of the label
    mylab.TextAlign = ContentAlignment.MiddleCenter;

    ```

*   **Step 3:** And last add this Label control to form using Add() method.

    ```cs
    // Add this label to the form
    this.Controls.Add(mylab);

    ```

    **示例:**

    ```cs
    using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace WindowsFormsApp16 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Creating and setting the label
            Label mylab = new Label();
            mylab.Text = "GeeksforGeeks";
            mylab.Location = new Point(222, 90);
            mylab.AutoSize = true;
            mylab.Font = new Font("Calibri", 18);
            mylab.BorderStyle = BorderStyle.Fixed3D;
            mylab.ForeColor = Color.Green;
            mylab.Padding = new Padding(6);
            mylab.TextAlign = ContentAlignment.MiddleCenter;

            // Adding this control to the form
            this.Controls.Add(mylab);

            // Creating and setting the label
            Label mylab1 = new Label();
            mylab1.Text = "Welcome To GeeksforGeeks";
            mylab1.Location = new Point(155, 170);
            mylab1.AutoSize = true;
            mylab1.BorderStyle = BorderStyle.Fixed3D;
            mylab1.Font = new Font("Calibri", 18);
            mylab1.Padding = new Padding(6);
            mylab.TextAlign = ContentAlignment.MiddleCenter;

            // Adding this control to the form
            this.Controls.Add(mylab1);
        }
    }
    }
    ```

    **输出:**
    ![](img/2a9ddd880009096b2b3e68cfdd12c274.png)