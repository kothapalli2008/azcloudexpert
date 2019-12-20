---
description: >-
  My goal here is to trigger an Azure DevOps pipeline with a single click.
  Triggering a pipeline can be done via Azure DevOps rest API and through
  PowerShell.
---

# Trigger Blue/Green deployment Pipelines with Flic button

In some situations, it can be useful to share the knowledge of what technology can do, especially at your work environment. I found these cute buttons while watching the twitch sessions with azure functions and Twilio. Flic is already an excellent integration with GitHub, Philips Hue and many more but I don't see integration with Azure DevOps and Pipelines.

My goal here is to trigger an Azure DevOps pipeline with a single click. Triggering a pipeline can be done via Azure DevOps rest API and through Powershell.

With this task you can trigger a build or release pipeline using flic button \(1 click to start green deployment , double-click to start blue database\)

Of course, to do that we need to have:

* A physical Flic Smart Button

![](../.gitbook/assets/image%20%2827%29.png) 

*  And downloaded Flic’s [Android](https://play.google.com/store/apps/details?id=io.flic.app) or [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) mobile app, that you will need to use it to pair one or more Flic Buttons.
* ![](../.gitbook/assets/image%20%284%29.png) 
* After you download the Flic mobile app, to configure the Flic Button you need to:
  * Make sure that your mobile has Bluetooth activated.
  * Open the Flic mobile app from your mobile phone, sign in with your credentials using Facebook, or by creating your Flic Account.
  * Once you login in the app, on the phone tab, click “Add Flic to Phone” at the bottom of the screen.
* ![](../.gitbook/assets/image%20%282%29.png) ****
* Once the “**Searching for Flics**” screen appears, take or physical button an click it once to pair it with the mobile application
* ![](../.gitbook/assets/image%20%2837%29.png) 
* Once the “**Pairing complete!**” screen appears, your button will be successfully paired with your phone. Click “**Finish” to complete**.
* ![](../.gitbook/assets/image%20%2838%29.png) 
* And a button will be added to the “**Phone**” tab
* ![](../.gitbook/assets/image%20%2835%29.png) 
* Now that the physical button is pair with our mobile phone, we need to configure the Flic’s events that the button will be triggering. For each button we can specify 3 types of events:
  * click \(one quick press\)
  * double-click \(two quick presses\)
  * hold \(one long press\)
* To accomplish that you need to:
  * Press the “**My Flic**” button present in the “**Phone**” tab
  * This will open the button configuration screen, there you should
    * Change the button name
    * And then configure one or all the 3 trigger events
* In our case, we will configure the “Click” trigger event to be able to trigger a Microsoft Flow. For that, we need to click on the “**Click**” option
* ![](../.gitbook/assets/image%20%2829%29.png) 
* On the “**Click**” trigger event list screen, select “**Advanced**” category option.
* And on the “Advanced” category list screen, select “**Microsoft Flow**” option.
* On the Flow screen you may or may not select to include GPS location and then you need to click “**SAVE** ” button.
* And our button will now be properly configured to trigger a Microsoft Flow once someone click \(one time\) the physical button

Now the only thing that is missing is for us to create a Flow that will be associated with this trigger event to fire up a Flow process.

*  Sign into [Microsoft Flow](https://flow.microsoft.com/)
  * You can create one flow from scratch
  * or by typing “flic” into the search box and select one of the several templates provided by Flow team.
* Click “**My flows”** option on the menu and then click “**+ Automated from blank**” to create a Flow from scratch.
* ![](../.gitbook/assets/image%20%2818%29.png) 
* On the “**Build an automated flow**”, Add the flowname "**flicdemo**" ,type "**flic**" in the flow's trigger text  and select "**When a Flic is pressed**"box and click "**create**".
* ![](../.gitbook/assets/image%20%2817%29.png) 
* On the Flic Trigger configuration
  * On “the Flic button” combo box, select the button we add create on the Mobile App earlier
  * And on the “Events” combo box, select “click” event that was the only one that we have configured
* \(of course, the first time you use this trigger, it will ask for permissions and you need to provide the authentication to your Flic account\)
* Add the next step by clicking “**+New step**” button and then choose the “**Add an action**” option
* ![](../.gitbook/assets/image%20%2823%29.png) 
* On the “**Choose an action**” window, enter “devops” and select the trigger “**create release**”.
*  ![](../.gitbook/assets/image%20%2842%29.png) 
* on the create a new release, you need to specify
  * The project name of the Azure Devops on the "Account name"
  * The projectname is "**flicdemo**"
  * And the release definationid is set to your blue deployment.
  * ![](../.gitbook/assets/image%20%2822%29.png) 
  * Be sure you **save it**.
  * Now… PRESS THE BUTTON! PRESS THE BUTTON!
  * The Flow was successfully triggered once I press the button.
  * ![](../.gitbook/assets/image%20%2820%29.png) 





