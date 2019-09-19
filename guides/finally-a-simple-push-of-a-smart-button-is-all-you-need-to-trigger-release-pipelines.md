---
description: A guide to  build servers and databases with Azure Devops & flic button.
---

# Create servers with flic button in azure

Today we will build a server and databases using :

* Azure Devops
* ARM Templates
* A Flic Button

If you don't own a Flic Button, [you can purchase one here](https://flic.io/shop/flic-1pack).

Before we begin, if you're looking for a quick summary and overview on Azure Devops Pipelines \(or found this page early and would like to get a headstart\), I recommend[ starting here with the documentation](https://azure.microsoft.com/en-us/services/devops/), or taking 4 minutes to read in more detail [how to create your first devops pipeline](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2) , so you have some context on how to use pipelines.

#### Let Us Begin!

Today we will trigger a azure devops pipelines using a Flic button. We will start by creating a release pipelines using azure devops. Then we will create a flic account, create flic actions to trigger release pipeline

Here's a diagram of what we'll be doing:

![](../.gitbook/assets/image.png)

### Create Azure Devops Account !

1. Browse to the Azure DevOps site at **http://dev.azure.com**
2. If you do not already have an account, click **Get started for free**
3. ![](../.gitbook/assets/image%20%2832%29.png) 
4. Authenticate with a Microsoft account.

### Create Demo Project 

1. Choose a name for your Project name. For the purposes of this scenario, we will use “FlicDemo” Choose Git for the source code and then click Create.
2. ![](../.gitbook/assets/image%20%2820%29.png) 
3. Once the Project is created, click on the **Repo** menu option in the left side navigation
4. ![](../.gitbook/assets/image%20%2817%29.png) 
5. On the **Repo** -&gt; File page for the **FlicDemo** repository, scroll down to the bottom of the page, then click on the **Initialize** button to get the “master” branch created.
6. ![](../.gitbook/assets/image%20%2825%29.png) 
7. Click on the **Clone** link in the upper-right
8. ![](../.gitbook/assets/image%20%287%29.png) 
9. Copy the **HTTPS URL** for the Git repository for use in the following step
10. ![](../.gitbook/assets/capture.PNG) 
11. When prompted, login with your Microsoft Account for your **Azure DevOps** Account
12. ![](../.gitbook/assets/image%20%282%29.png) 

### Author ARM Templates 

1. Open Visual Studio and create a new project of the type Cloud – Azure Resource Group. Name the new project “**FlicDemo.AzureResourceTemplate**” and save it to C:\Repo. Also, make sure that both check boxes are checked on the lower right, as in the screen shot below. When finished, click **OK**.
2. ![](../.gitbook/assets/image%20%2814%29.png) 
3. On the next window, click **Blank Template**, and click **OK**.
4. ![](../.gitbook/assets/image%20%285%29.png) 
5. In the Solution Explorer window, open the **azuredeploy.json** file by double-clicking it.
6. ![](../.gitbook/assets/image%20%2822%29.png) 
7. Then, probably on the left side of the Visual Studio window, open the window called **JSON** Outline. It will look like this screen shot.
8. ![](../.gitbook/assets/image%20%2830%29.png) 
9. Save your Files

### Add Azure SQL Database and server to the template

1. Right-click on the **resources** item in the **JSON Outline** and click **Add New Resource**.
2. Select **SQL Server** and give it a name like “**flicdemo**”, then click **Add**.
3. ![](../.gitbook/assets/image%20%2823%29.png) 
4. Now that the **SQL Server** has been created as a resource, right-click that **SQL Server resource** and choose **Add New Resource** so that you can add a **database.**
5. \*\*\*\*![](../.gitbook/assets/image%20%2823%29.png) ****
6. Choose SQL Database, and call it “**flicdemodatabase**.” Make sure that your server is selected in the drop-down list below, and click Add.
7.  **** ![](../.gitbook/assets/image%20%2818%29.png) 

### Create your First CI&CD Pipelines 

### Lets Trigger a pipeline using Flic Button 











