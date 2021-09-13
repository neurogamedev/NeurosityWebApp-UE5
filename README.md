# NeurosityWebApp-UE5

![GitHub](https://img.shields.io/github/release/neuromodgames/NeurosityWebApp-UE5?style=for-the-badge)
![GitHub](https://img.shields.io/github/license/neuromodgames/NeurosityWebApp-UE5?style=for-the-badge)

UE5 example project. Log into your Neurosity account, choose your device, and see: device status, calm and focus scores.

![ezgif-7-f0b21b1f1c52](https://user-images.githubusercontent.com/88777150/133000227-3b8ded89-0a13-4751-9d4b-a08032fb030b.gif)

## What can you do with it?

You can use this example to connect to your Neurosity account and devices. It is up to you to build upon it and make your own apps and games!

## The shoulders of giants

This project was built upon the hard work of others. As such, it is also dependent on the scrutiny and update of the tools they so generously provide. Make sure to check their sites and repositories if you want to upgrade your own project or if you want to try your hand at older versions of Unreal Engine.

- Thanks to [AJ Keller](https://www.linkedin.com/in/andrewjaykeller/) and [Alex Castillo](https://www.linkedin.com/in/alexcas/) for coming up with the [Crown](https://neurosity.co/) hardware and the [Neurosity SDK](https://docs.neurosity.co/docs/overview). 

- Thanks to [Jan Kaniewski](https://github.com/getnamo) for developing the [Node.js plugin](https://github.com/getnamo/nodejs-ue4) for Unreal Engine 5. 

- Thanks to Epic Games, Inc. for making [Unreal Engine 5](https://www.unrealengine.com/) accessible for everyone.

## Where's the important stuff?

The magic happens in the *NeurosityApp.js* in the *NeurosityWebApp\Content\Scripts* folder. It's inundated with helpful comments! You cannot see it directly in the Editor, you have to look for it using your file explorer and open it in your favorite code editor.

You can find all my blueprints in the *Content/Maps/WebApp/Core* folder, inside the Editor. Don't forget to also open the Level Blueprint to see how it all starts!

The *BP_NeurosityNodejs* does all of the communication between *NeurosityApp.js* and Unreal. This is a prime candidate for your first singleton.

The *WBP_WebAppGUIManager* is the interface between the end user and *BP_NeurosityNodejs*. This is your prime suspect when button logic goes awry.

## How can I set up my own from scratch?

1. Download and install [Unreal Engine](https://www.unrealengine.com/en-US/download). Sign up or sign in as necessary.
2. Download and install [Git](https://git-scm.com/).
3. Download and install [Node.js](https://nodejs.org/en/).
4. Download the [Node.js plugin](https://github.com/getnamo/nodejs-ue4). Also download the [SocketIO Client plugin](https://github.com/getnamo/socketio-client-ue4) if you're downloading the Node.js plugin v0.7.0 for UE 4.26 or below.
5. Create a new project if you haven't made a project already.
6. Browse to your project folder (typically found at *.../Documents/Unreal Project/{Your Project Root}*).
7. Copy *Plugins* folder from the *Node.js plugin* download into your Project root. If working with an older version of the plugin, also place the aforementioned *socketio-client-ue4* folder in the Plugins folder.
8. Create a *Scripts* folder inside the *{Your Project Root}/Contents* folder. The name and location is very important for the plugin to run.
9. Copy/paste the *node_modules* folder from *{Your Project Root}/Plugins/nodejs-ue4/Content/Scripts* folder to your *{Your Project Root}/Contents/Scripts* folder.
10. Follow the setup instructions and install dependencies in your *{Your Project Root}/Contents/Scripts* folder, just as you would in [Your First Node App](https://docs.neurosity.co/docs/getting-started) example project. Ignore the section where you authenticate with an .env file. The plugin doesn't support that workflow.
11. Open your project in Unreal Engine. It is not necessary to "Import Changes", but make sure the Node.js and the SocketIO plugins are enabled.
12. You're good to start your own journey! Check this very example project or [getnamo's examples](https://github.com/getnamo/nodejs-ue4) to figure out how to use [Neurosity's SDK](https://docs.neurosity.co/docs/overview) with the Node.js plugin.

## Packaging

Make sure to add the folder where your project Scripts are as additional non-asset directories to copy relative to the Content directory (e.g. for the typical Content/Scripts folder add just Scripts).

![image](https://user-images.githubusercontent.com/88777150/133001784-82c17074-3fe2-40ec-a41b-ffab2cab2fe1.png)

## Caveats

- You won't be able to see your javascripts inside the UE editor. You'll have to access them from the file explorer and open them in your favorite code editor.
- So far I have only been able to successfully package this project for Windows, sometimes login crashes.
- Trying to package for Android throws an otherwise unexpected "Error: Windows.h not found". I suspect the issue lies with the Node.js plugin.
- The Event Tick in the WBP_WebAppGUIManager may not be super efficient. Suggestions are welcome.

## To Do

- Check why the packaged game has trouble logging in when run on another computer.
- Check if the packaged game runs in a computer where Node.js has not been installed. 
- Check if the game can be packaged for, and run in, an iOS platform.
- Fix the Android packaging error.

## Frequently Asked Questions

**Q: Why are there no questions here?**

A: People haven't yet asked me questions to populate this section.
