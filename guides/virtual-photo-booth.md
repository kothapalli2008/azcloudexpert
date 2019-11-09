---
description: >-
  IoT Photo Booth project utilizes Vision AI DevKit to create captures of
  persons. These captures are further processed using Azure Stream Analytics,
  Twilio and Azure SignalR services.
---

# Implement IoT Photo Booth

## Summary

This is a quick proof of concept using various Azure AI services that allows the users to take the pictures at the photo booth without any human interaction using the power of Artificial Intelligence. This project builds on the basic features already installed in the Vision AI DevKit getting started Module, Custom Build Capture Module. Using the default ML model for object detection, this project takes a screenshot when one or more people are detected in frame. It send these data to cloud \(using IoTHub\). Data is processed using [**Azure Stream Analytics**](https://azure.microsoft.com/en-us/services/stream-analytics/), while the most important part is, that the processing consist also from [**Cloudinary**  ](https://cloudinary.com)API, thanks to which we are able to transform pictures real-time, [**Twilio**](https://www.twilio.com/) to send the pictures as a Text message and [**Azure SignalR**](https://azure.microsoft.com/en-us/services/signalr-service/) ****service to display the pictures on TV, when the person is identified. Solution is proactively sending notifications after there is a new person in the photo booth area, to TV and mobile device. For further details see architecture of solution below:

## Implementation

## Software's Used 

## Repository

## Future Improvements



```
$ give me super-powers
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```
// Ain't no code for that yet, sorryecho 'You got to trust me on this, I saved the world'
```



