# Setting up Mock API with Azure Function Proxies

Recently, while I am working on a project with Node, Azure cloud, ARM Templates, and Azure DevOps, I need to test my front end application and realized the back end API is not ready yet. Then I want to add this exciting feature not to wait until the back end is available.

## **Let's get started** <a id="SettingupMockAPIwithAzureFunctionProxies-Let&apos;sgetstarted"></a>

1. Navigate to the Azure Management portal, [http://portal.azure.com](http://portal.azure.com/).
2. Select **+ New**, then type function into the search box on top. Select **Function App** from the results.
3. ![](https://visionworks.atlassian.net/wiki/download/thumbnails/783450310/image2019-9-22_23-42-36.png?version=1&modificationDate=1569213758312&cacheVersion=1&api=v2&width=838&height=250)
4. Select the **Create** button on the Function App overview blade.
5. On the Create Function App blade, specify the following configuration options:
   1. Name: unique value for the App name \(ensure the green checkmark appears\). Provide a name similar to **pricingcalculatormockapi**
   2. Specify the Resource Group "**RETAIL-DEV-CUS-PRICINGCALCULATOR-RG**"
   3. Select the **App Service Plan** Hosting Plan.
   4. Select the same location as your Resource Group.
   5. Leave the storage option as create new.
   6. Ensure Off is selected for Application Insights \(we’ll add this later\).
   7. ![](https://visionworks.atlassian.net/wiki/download/thumbnails/783450310/image2019-9-22_23-48-21.png?version=1&modificationDate=1569214103192&cacheVersion=1&api=v2&width=143&height=400)
   8. select **Create.**
   9. ![](https://visionworks.atlassian.net/wiki/download/attachments/783450310/image2019-9-22_23-49-4.png?version=1&modificationDate=1569214145529&cacheVersion=1&api=v2)
6. After the function app is created navigate to function as shown below.
7. ![](https://visionworks.atlassian.net/wiki/download/thumbnails/783450310/image2019-9-22_23-50-51.png?version=1&modificationDate=1569214252650&cacheVersion=1&api=v2&width=573&height=250)

## **Azure Function Proxies** <a id="SettingupMockAPIwithAzureFunctionProxies-AzureFunctionProxies"></a>

Functions Proxies are currently in public. With them, any function app can now define an endpoint that serves as a reverse proxy to another \[API /webhook/function App/anything else\].  
Before being able to create new Azure Functions Proxies, you need to enable them. From the Function blade, select the _Settings_ tab on the top of the screen, then click the _On_ button, under the Proxie section.

![](https://visionworks.atlassian.net/wiki/download/thumbnails/783450310/image2019-9-22_23-53-58.png?version=1&modificationDate=1569214439524&cacheVersion=1&api=v2&width=379&height=250)

Now let's create our first Function Proxy. Click on the "**+**" on the right of _Proxies_ . Enter the following values.  


![](https://visionworks.atlassian.net/wiki/download/thumbnails/783450310/image2019-9-22_23-55-48.png?version=1&modificationDate=1569214550269&cacheVersion=1&api=v2&width=470&height=400)

## **Try It** <a id="SettingupMockAPIwithAzureFunctionProxies-TryIt"></a>

**I will cover the CI/CD for Azure function in the upcoming article. For now, we will launch the browser and type the URL. It will return the response.** 

![](https://visionworks.atlassian.net/wiki/download/attachments/783450310/image2019-9-23_0-11-18.png?version=1&modificationDate=1569215480307&cacheVersion=1&api=v2)

**For Detailed information or step by step please follow the referenced articles.**

## **References** <a id="SettingupMockAPIwithAzureFunctionProxies-References"></a>

1. [https://docs.microsoft.com/en-us/azure/azure-functions/functions-proxies](https://docs.microsoft.com/en-us/azure/azure-functions/functions-proxies)
2. [https://msdn.microsoft.com/magazine/mt814805.aspx](https://msdn.microsoft.com/magazine/mt814805.aspx)
3. [https://www.serverless360.com/blog/azure-function-proxies](https://www.serverless360.com/blog/azure-function-proxies)
4. [https://www.freecodecamp.org/news/introduction-to-azure-function-proxies](https://www.freecodecamp.org/news/introduction-to-azure-function-proxies/).

{% embed url="https://www.youtube.com/watch?v=jzSVc3WpK\_k" %}









