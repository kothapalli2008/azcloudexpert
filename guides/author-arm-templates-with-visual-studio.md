---
description: >-
  You will learn how to create and deploy virtual machines in Azure using the
  ARM templates including deploying custom images and Linux virtual machines.
---

# Author ARM Templates with Visual Studio

1. Open Visual Studio 2017/2019 and create a new project of the type Cloud – Azure Resource Group. Name the new project “**Demo.AzureResourceTemplate**” and save it to C:\Repo. Also, make sure that both check boxes are checked on the lower right, as in the screen shot below. When finished, click **OK**.
2. ![](../.gitbook/assets/image%20%2815%29.png)
3. On the next window, click **Blank Template**, and click **OK**.
4. ![](../.gitbook/assets/image%20%286%29.png)
5. In the Solution Explorer window, open the **azuredeploy.json** file by double-clicking it.
6. ![](../.gitbook/assets/image%20%2824%29.png)
7. Then, probably on the left side of the Visual Studio window, open the window called **JSON** Outline. It will look like this screen shot.
8. ![](../.gitbook/assets/image%20%2833%29.png)
9. Save your Files

### Add Azure SQL Database and server to the template

1. Right-click on the **resources** item in the **JSON Outline** and click **Add New Resource**.
2. Select **SQL Server** and give it a name like “**demo**”, then click **Add**.
3. ![](../.gitbook/assets/image%20%2825%29.png)
4. Now that the **SQL Server** has been created as a resource, right-click that **SQL Server resource** and choose **Add New Resource** so that you can add a **database.**
5. ![](../.gitbook/assets/image%20%2825%29.png)
6. Choose SQL Database, and call it “**demodatabase**.” Make sure that your server is selected in the drop-down list below, and click Add.
7. ![](../.gitbook/assets/image%20%2819%29.png)
8. 
