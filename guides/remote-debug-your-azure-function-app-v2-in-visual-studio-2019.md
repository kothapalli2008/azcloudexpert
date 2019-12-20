# Remote debug your azure function app v2 in Visual Studio 2019

**Sometimes while i am working with function app \(Copy file from on-Premise server to Azure blob storage account\) it works fine on my local machine and when you try to publish it publishes OK, However the function is getting triggered but it doesn't copy the file to  Azure Blob.**

Now to debug the function app i did the following:

* Have a Function App deployed to the Azure platform and had a Hybrid connection\(V-Net Integration\) to communicate with the on-prem server.
* Attach a remote debugger to the Function app
* Confirm the remote debugger is attached to the W3WP process.
* Set the break points.
* Execute the process which is rendering the exception, performing slow or in an unexpected manner.

## Deploying Azure Function App to Azure Platform

In this step, you will publish the Function App from the starter project in Visual Studio to the existing Function App you provisioned in Azure.

1. Navigate to the **FileProcessor** project using the Solution Explorer of Visual Studio
2. Right-click the **FileProcessor** project and select Publish… from the context menu.

![](../.gitbook/assets/image%20%2820%29.png)

![](../.gitbook/assets/image%20%281%29.png)

In the Publish window that appears, make sure **Azure Function App** is selected, choose the Select Existing radio button, then select **Publish**.

In the App Service form, select your **Subscription**, select **Resource Group** under View, then expand your resource group and select the Function App  . Whatever you named the Function App when you provisioned it is fine.

After you select the Function App, select **OK**.

![](../.gitbook/assets/image%20%2831%29.png)

Watch the Output window in Visual Studio as the Function App publishes. When it is finished, you should see a message that says, “**Publish Succeeded.**”

Using a new tab or instance of your browser navigate to the Azure Management portal, h[ttp://portal.azure.com](http://portal.azure.com).

Open the  resource group, then select the Azure Function App to which you just published.

## Attach a remote debugger to the Function app

## Confirm the remote debugger is attached to the W3WP process

## Set the break points

## Execute the process which is rendering the exception, performing slow or in an unexpected manner







