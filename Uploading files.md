# Uploading files

1. **Create an ASP.NET Web Forms or MVC Project:**
   Start by creating a new ASP.NET project in Visual Studio.

2. **Create an HTML Form (Web Forms):**
   In Web Forms, create a page with an HTML form that includes an input of type file.

   ```html
   <%@ Page Language="C#" AutoEventWireup="true" CodeBehind="FileUpload.aspx.cs" Inherits="YourNamespace.FileUpload" %>

   <!DOCTYPE html>

   <html xmlns="http://www.w3.org/1999/xhtml">
   <head runat="server">
       <title>File Upload Example</title>
   </head>
   <body>
       <form id="form1" runat="server">
           <div>
               <input type="file" id="fileUpload" runat="server" />
               <asp:Button ID="btnUpload" runat="server" Text="Upload" OnClick="btnUpload_Click" />
           </div>
       </form>
   </body>
   </html>
   ```

3. **Handle File Upload in Code-Behind (Web Forms):**
   In the code-behind file (FileUpload.aspx.cs), handle the file upload in the button click event.

   ```csharp
   using System;
   using System.IO;

   namespace YourNamespace
   {
       public partial class FileUpload : System.Web.UI.Page
       {
           protected void btnUpload_Click(object sender, EventArgs e)
           {
               if (fileUpload.HasFile)
               {
                   try
                   {
                       string fileName = Path.GetFileName(fileUpload.FileName);
                       string filePath = Server.MapPath("~/Uploads/") + fileName;
                       fileUpload.SaveAs(filePath);
                       // You can do further processing here
                       Response.Write("File uploaded successfully!");
                   }
                   catch (Exception ex)
                   {
                       Response.Write("Error: " + ex.Message);
                   }
               }
               else
               {
                   Response.Write("Please select a file to upload.");
               }
           }
       }
   }
   ```

4. **Create an Uploads Folder:**
   Make sure you create a folder named "Uploads" in your project to store the uploaded files.

   ```plaintext
   YourProject
   ├── Uploads
   ├── FileUpload.aspx
   ├── FileUpload.aspx.cs
   └── ...
   ```

This is a basic example, and you may need to add more error handling, security checks, and possibly validation depending on your application's requirements. Additionally, if you're using ASP.NET MVC, the process is a bit different, involving controller actions and views.
