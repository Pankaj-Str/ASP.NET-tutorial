### Create a basic Windows Form application using **ASP.NET Windows Forms** (although typically, ASP.NET is used for web applications, and Windows Forms for desktop). If you’re looking to create a form in a Windows Forms desktop app using C# in **Visual Studio**, here’s a simple example.

### Step 1: Create a New Windows Forms App

1. Open **Visual Studio**.
2. Click on **Create a new project**.
3. Select **Windows Forms App (.NET Framework)** and click **Next**.
4. Set your **Project name** (e.g., `MyWindowsFormApp`) and choose the **.NET Framework** version.
5. Click **Create**.

### Step 2: Design the Form

You will see a blank Windows Form in the designer. You can add controls (such as labels, text boxes, buttons) from the **Toolbox** on the left.

1. Drag and drop controls from the **Toolbox** onto your form.

Here’s an example form with a **Label**, **TextBox**, and **Button**.

- **Label**: Displays text that says "Enter Your Name."
- **TextBox**: Accepts user input.
- **Button**: Submits the form.

### Step 3: Add Controls

1. **Add a Label**:
   - Drag a **Label** from the **Toolbox** to your form.
   - Set its `Text` property to "Enter Your Name" in the **Properties** panel.

2. **Add a TextBox**:
   - Drag a **TextBox** from the **Toolbox** to the form below the label.
   - Name it `txtName` in the **Properties** panel.

3. **Add a Button**:
   - Drag a **Button** to the form below the TextBox.
   - Set its `Text` property to "Submit" and name it `btnSubmit`.

### Step 4: Add Code to the Button

1. Double-click the **Submit** button to open the **code-behind** file.
2. Add code to display a message box when the user clicks the button.

Here's the sample code for your form:

```csharp
using System;
using System.Windows.Forms;

namespace MyWindowsFormApp
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnSubmit_Click(object sender, EventArgs e)
        {
            string userName = txtName.Text;
            MessageBox.Show("Hello, " + userName + "!", "Greetings");
        }
    }
}
```

### Explanation

- **`txtName.Text`** gets the text entered by the user.
- **`MessageBox.Show`** displays a message box with a greeting.

### Step 5: Run the Application

1. Press **F5** or click on **Start** in Visual Studio to run your application.
2. The form will appear, allowing you to enter a name, click **Submit**, and see the greeting message.

This simple form provides a user-friendly interface to collect input and display it in a message box. Let me know if you’d like to add more features!
