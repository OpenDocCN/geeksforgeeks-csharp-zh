# 如何在 C#中设置 NumericUpDown 中文本的对齐方式？

> 原文:[https://www . geeksforgeeks . org/如何设置 c-sharp 中 numericupdown 中文本的对齐方式/](https://www.geeksforgeeks.org/how-to-set-the-alignment-of-the-text-in-numericupdown-in-c-sharp/)

在 Windows 窗体中，NumericUpDown 控件用于提供显示数值的 Windows 旋转框或上下控件。或者换句话说，NumericUpDown 控件提供了一个使用上下箭头移动并保存一些预定义数值的界面。在 NumericUpDown 控件中，可以使用**文本对齐属性**设置上下控件中文本的对齐方式。此属性包含在水平对齐枚举下定义的三个不同的值，这些值是:

*   *居中*:将文本对齐 NumericUpDown 控件的中心。
*   *左侧*:将 NumericUpDown 控件左侧的文字对齐。
*   *右侧*:将文本对齐 NumericUpDown 控件右侧。

该属性的默认值保持不变。您可以通过两种不同的方式设置此属性:

**1。设计时:**最简单的方法是在 NumericUpDown 中设置文本的对齐方式，如以下步骤所示:

*   **第一步:**创建如下图所示的窗口表单:
    **Visual Studio->File->New->Project->windows formpp**
    ![](img/de9202f1f4646167e60ea580d67273d9.png)
*   **Step 2:** Next, drag and drop the NumericUpDown control from the toolbox on the form as shown in the below image:

    ![](img/e130871c36b969be4b9cf9ab8e45a276.png)

*   **Step 3:** After drag and drop you will go to the properties of the NumericUpDown and set the alignment of the text in the NumericUpDown as shown in the below image:

    ![](img/2c4dbeb39fb9aa873dfff4e1192c9113.png)

    **输出:**

    ![](img/21adcd9cea1096098c073896c5fddf9e.png)

**2。运行时:**比上面的方法稍微复杂一点。在此方法中，您可以在给定语法的帮助下以编程方式设置 NumericUpDown 控件中文本的对齐方式:

```
public System.Windows.Forms.HorizontalAlignment TextAlign { get; set; }
```

这里，水平对齐表示该属性的值。如果该属性的值不属于水平对齐枚举，那么它将抛出*InvalidEnumArgumentException*。以下步骤显示了如何动态设置 NumericUpDown 中文本的对齐方式:

*   **步骤 1:** 使用 numericpdown()构造函数创建 numericpdown，该构造函数由 numericpdown 类提供。

    ```
    // Creating a NumericUpDown
    NumericUpDown n = new NumericUpDown();

    ```

*   **第二步:**创建 numericpdown 后，设置 numericpdown 类提供的 numericpdown 的 TextAlign 属性。

    ```
    // Setting the TextAlign
    n.TextAlign = HorizontalAlignment.Right;

    ```

*   **Step 3:** And last add this NumericUpDown control to the form using the following statement:

    ```
    // Adding NumericUpDown control on the form
    this.Controls.Add(n);

    ```

    **示例:**

    ```
    using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace WindowsFormsApp44 {

    public partial class Form1 : Form {

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

            // Creating and setting the
            // properties of the labels
            Label l1 = new Label();
            l1.Location = new Point(348, 61);
            l1.Size = new Size(215, 25);
            l1.Text = "Example";
            l1.Font = new Font("Bodoni MT", 16);
            this.Controls.Add(l1);

            Label l2 = new Label();
            l2.Location = new Point(242, 136);
            l2.Size = new Size(103, 20);
            l2.Text = "Select value:";
            l2.Font = new Font("Bodoni MT", 12);
            this.Controls.Add(l2);

            // Creating and setting the
            // properties of NumericUpDown
            NumericUpDown n = new NumericUpDown();
            n.Location = new Point(386, 130);
            n.Size = new Size(126, 26);
            n.Font = new Font("Bodoni MT", 12);
            n.Value = 18;
            n.Minimum = 18;
            n.Maximum = 30;
            n.Increment = 1;
            n.TextAlign = HorizontalAlignment.Right;

            // Adding this control
            // to the form
            this.Controls.Add(n);
        }
    }
    }
    ```

    **输出:**
    ![](img/1cf713a4d8ef358822255a89fe729402.png)