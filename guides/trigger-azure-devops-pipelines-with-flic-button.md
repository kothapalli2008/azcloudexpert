---
description: >-
  My goal here is to trigger an Azure DevOps pipeline with a single click.
  Triggering a pipeline can be done via Azure DevOps rest API and through
  PowerShell.
---

# Trigger Azure DevOps Pipelines with Flic button

In some situations, it can be useful to share the knowledge of what technology can do especially at your work environment. I found these nice buttons while watching the twitch sessions with azure functions and Twilio. Flic is already a nice integration with GitHub, Philips Hue and many more but I don't see integration with Azure DevOps and Pipelines 

My goal here is to trigger an Azure DevOps pipeline with single click. Triggering a pipeline can be done via Azure DevOps rest API and through powershell.

With this task you can trigger a build or release pipeline using flic button \(1 click to start deploying webapp , double-click to start deploying database\)

Of course, to do that we need to have:

* A physical Flic Smart Button

![](../.gitbook/assets/image%20%2812%29.png) 

*  And downloaded Flic’s [Android](https://play.google.com/store/apps/details?id=io.flic.app) or [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) mobile app, that you will need to use it to pair one or more Flic Buttons.
* ![](../.gitbook/assets/image%20%283%29.png) 
* After you download the Flic mobile app, to configure the Flic Button you need to:
  * Make sure that your mobile has Bluetooth activated.
  * Open the Flic mobile app from your mobile phone, sign in with your credentials using Facebook, or by creating your Flic Account.
  * Once you login in the app, on the phone tab, click “Add Flic to Phone” at the bottom of the screen.
* ![](../.gitbook/assets/image%20%281%29.png) ****
* Once the “**Searching for Flics**” screen appears, take or physical button an click it once to pair it with the mobile application
* ![](../.gitbook/assets/image%20%2819%29.png) 
* Once the “**Pairing complete!**” screen appears, your button will be successfully paired with your phone. Click “**Finish” to complete**.
* ![](../.gitbook/assets/image%20%2820%29.png) 
* And a button will be added to the “**Phone**” tab
* ![](../.gitbook/assets/image%20%2817%29.png) 
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
* In our case, we will configure the “**Click**” trigger event to be able to trigger a Microsoft Flow. For that, we need to click on the “**Click**” option
* ![](../.gitbook/assets/image%20%2814%29.png) 





