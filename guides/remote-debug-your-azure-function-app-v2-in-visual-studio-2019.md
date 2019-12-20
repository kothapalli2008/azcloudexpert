# Remote debug your azure function app v2 in Visual Studio 2019

**Sometimes while i am working with function apps it works fine on my local machine and when you try to publish it publishes OK, However the function is getting triggered but it doesn't perform the action what the function app is suppose to perform.**

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

![](../.gitbook/assets/image%20%2827%29.png)

![](../.gitbook/assets/image%20%281%29.png)

In the Publish window that appears, then select **Publish**.

In the App Service form, select your **Subscription**, select **Resource Group** under View, then expand your resource group and select the Function App  . Whatever you named the Function App when you provisioned it is fine.

After you select the Function App, select **OK**.

![](../.gitbook/assets/image%20%2842%29.png)

Watch the Output window in Visual Studio as the Function App publishes. When it is finished, you should see a message that says, “**Publish Succeeded.**”

Using a new tab or instance of your browser navigate to the Azure Management portal, h[ttp://portal.azure.com](http://portal.azure.com).

Open the  resource group, then select the Azure Function App to which you just published.

## Attach a remote debugger to the Function app

Within Visual Studio open the Cloud Explorer, expand the Web Apps, right-click the Web App you want to attach to and click Attach Debugger, as shown in Figure 1.  You can download Cloud Explorer [here ](https://visualstudiogallery.msdn.microsoft.com/84e83a7c-9606-4f9f-83dd-0f6182f13add)or install it from within Visual Studio by selecting Tools -&gt; Extensions and Updates..., then search for Cloud Explorer.

![Attach a remote debugger to a Microsoft Function App](../.gitbook/assets/image%20%289%29.png)

If you have not already enabled the remote debugging application setting, it will be done for you when you attach the debugger for the first time. You can see the setting in the azure portal as shown below

.

![](../.gitbook/assets/image%20%285%29.png)



## Confirm the remote debugger is attached to the W3WP process

After the Web App opens in the browser return to Visual Studio and click on Debug –&gt; Attach to Process…. Then select the Function App to which you want to debug from the Qualifier drop down as shown in Figure

{% hint style="info" %}
Many times, this won’t work or you get an error. you can works this by attaching the debugger manually in Visual Studio. 
{% endhint %}

*  Go to the **Debug** menu and select **Attach to Process…**
* \*\*\*\*

![](../.gitbook/assets/image%20%2813%29.png)

* Enter the url + port number of your function app in the Connection target field like this: [https://fileprocessorappserviceplan.azurewebsites.net](https://fileprocessorappserviceplan.azurewebsites.net/):4024
* You can find the right port number in this [document](https://docs.microsoft.com/en-us/visualstudio/debugger/remote-debugger-port-assignments?view=vs-2017). In my example it is the port number for Visual Studio 2017. For 2019 it is 4024.
* When prompt to authenticate, you can do this with the publish profile of your Function App. Download the publish profile by hitting the **Get publish profile** button in the Azure portal. Use the **userName** and **userPWD** of the publish profile.
* 
![](../.gitbook/assets/image%20%2812%29.png)



![](../.gitbook/assets/image%20%2834%29.png)

* Because it is a .NET Core application, we need to set **Attach to** to **Managed \(CoreCLR\) code**. You can do this with the select button. 
* Last thing is to select the **w3wp.exe** process and hit **Attach**.
* Let Visual Studio download all the files needed en you can debug your application as if you’re working locally.
* 
![](../.gitbook/assets/image%20%2811%29.png)

Once confirmed move on and start debugging.

## Set the break points

When you attach the debugger to your Function App it will open the Function App in you browser. Leave the browser open but change the focus to Visual Studio and set your breakpoints just like you would when debugging locally.

* Debug must be = true

{% hint style="info" %}
The Version of the Dlls should match with the local version.
{% endhint %}

* set a break point to troubleshoot the code 
* 
![](../.gitbook/assets/image%20%2835%29.png)

* Navigate back to the browser where your Fucntion App is displayed, the example code Function App looks like this:
* 
![](../.gitbook/assets/image%20%287%29.png)

## Execute the process which is rendering the exception, performing slow or in an unexpected manner

Just like when debugging locally, as I have set a break point on the Function App. Thats it.

![](../.gitbook/assets/image%20%286%29.png)

Happy Coding !!

