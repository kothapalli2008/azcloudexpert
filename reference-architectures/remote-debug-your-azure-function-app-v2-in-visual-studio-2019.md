# Remote debug your azure function app v2 in Visual Studio 2019

Sometimes while I am working with function apps, it works fine on my local machine, and when you try to publish it publishes OK. However, the function is getting triggered, but it doesn't act what the function app is supposed to perform.

Now to debug the function app, I did the following:

* Have a Function App deployed to the Azure platform and had a Hybrid connection\(V-Net Integration\) to communicate with the on-prem server.
* Attach a remote debugger to the Function app
* Confirm the remote debugger is attached to the W3WP process.
* Set the breakpoints.
* Execute the process which is rendering the exception, performing slow or in an unexpected manner

## **Deploying Azure Function App to Azure Platform**

In this step, you will publish the Function App from the starter project in Visual Studio to the existing Function App you provisioned in Azure.

1. Navigate to the FileProcessor project using the Solution Explorer of Visual Studio
2. Right-click the FileProcessor project and select Publish from the context menu.

![](../.gitbook/assets/image%20%282%29.png)

![](../.gitbook/assets/image%20%2836%29.png)

If you have not already enabled the remote debugging application setting, it will be done for you when you attach the debugger for the first time. You can see the setting in the Azure portal as shown below

![](../.gitbook/assets/image%20%2817%29.png)

## Confirm the remote debugger is attached to the W3WP process

After the Web App opens in the browser, return to Visual Studio and click on Debug –&gt; Attach to Process Then select the Function App to which you want to debug from the Qualifier drop-down as shown in Figure

Many times, this won’t work, or you get an error. You can work this by attaching the debugger manually in Visual Studio.

Go to the **Debug** menu and select **Attach to Process**

![](../.gitbook/assets/image%20%2819%29.png)

Enter the URL + port number of your function app in the Connection target field like this: [fileprocessorappserviceplan.azurewebsites.net](https://fileprocessorappserviceplan.azurewebsites.net/):4024

You can find the right port number in this [document](https://docs.microsoft.com/en-us/visualstudio/debugger/remote-debugger-port-assignments?view=vs-2017). In my example, it is the port number for Visual Studio 2017. For 2019 it is 4024.

When prompt to authenticate, you can do this with the publish profile of your Function App. Download the publish profile by hitting the **Get publish profile** button in the Azure portal. Use the **userName** and **userPWD** of the publish profile.

![](../.gitbook/assets/image%20%284%29.png)

![](../.gitbook/assets/image%20%283%29.png)

Because it is a .NET Core application, we need to set **Attach to** to **Managed \(CoreCLR\) code**. You can do this with the select button.

Last thing is to select the **w3wp.exe** process and hit **Attach**.

Let Visual Studio download all the files needed en you can debug your application as if you’re working locally.

![](../.gitbook/assets/image%20%286%29.png)

Once confirmed move on and start debugging.

## Set the breakpoints

When you attach the debugger to your Function App it will open the Function App in you browser. Leave the browser open but change the focus to Visual Studio and set your breakpoints just like you would when debugging locally.

* Debug must be = true
* The Version of the Dlls should match with the local version.
* set a breakpoint to troubleshoot the code

![](../.gitbook/assets/image%20%2851%29.png)

Navigate back to the browser where your Function App is displayed, the example code Function App looks like this:

![](../.gitbook/assets/image%20%2852%29.png)

## Execute the process which is rendering the exception, performing slow or in an unexpected manner

Just like when debugging locally, as I have set a break point on the Function App. Thats it.

![](../.gitbook/assets/image%20%2842%29.png)

Happy Coding !!

