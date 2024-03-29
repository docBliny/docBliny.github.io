# Roon playback control for Elgato Stream Deck
This is a plug-in that allows controlling music playback of Roon outputs with the Elgato Stream Deck.

Unfortunately, I don't have time to support this project. Let me know if you're interested in taking ownership.

Don't have Roon? Use my referral link: [Purchase Roon](https://roonlabs.com/r/flf4BxfNwEagR1t5ZBqYUA)

**NOTE!** Roon version 1.8 (Build 882) made the Roon port more random than it used to be. You'll likely have to do a bit of hunting to find the right one

## Features
The plug-in supports most basic playback actions. Note that some actions are available in two flavors. For example, there is a Play/Pause action in addition to separate Play and Pause actions. "Why?" you might ask. Well, if you're streaming you want to be sure you're hitting the right button to actually start or stop playback. They're also easier to use in multi-actions.

![Screen shot](images/screenshot.png)

- Play/Pause
  - Cover art (optional)
  - Elapsed playback time (optional)
- Play
- Pause
- Stop (may pause instead)
- Play playlist, tags, artist, album
- Play related artist/album
- Previous
- Next
- Loop mode (all/one/off)
- Shuffle mode (on/off)
- Volume up
- Volume down
- Volume set
- Mute/Unmute
- Roon radio on/off

You can hold the volume up/down buttons instead of pressing them down multiple times, and you can hold down the previous/next buttons to seek within a track.

To play specific playlists, artists, radio station, etc. you'll need to match the name exactly with what's in Roon. You'll get a warning image if no match is found.

## Installation
There are three basic steps required to get started with the plug-in:
1. Install the Stream Deck plug-in.
2. Configure your Roon Core address.
3. Enable the plug-in extension in Roon.

### Step 1: Stream Deck plug-in installation
Install the plug-in from the Stream Deck store. Just click on **More Actions..**, type in `Roon` in the search box, and then click the **Install** button. See below.

![Search and install](images/search-install.png)

### Step 2: Roon Core configuration
- Once the plug-in is installed, scroll down in the list until you find the `Roon` category.
- Add one of the Roon actions, such as _Play/Pause_, to the Deck.
- You'll see the Roon core section in the button configuration. This is only expanded when you haven't configured the address of your Roon Core, but you can alway get back to it by clicking on the expansion triangle.
- Enter the hostname (or IP address) and port of your Roon Core. NOTE! The port number is random. You can check Roon Settings / Displays / Web display URL for the likely port number.
- Click **Connect**.

At this point, assuming the address is correct and your computer is able to reach the Roon Core, you'll need to enable the extension in Roon.

> Tip: You only need to configure the Roon Core once. While the connection options show up for each button, the settings under this section are shared across all buttons.

![Configure Roon Core](images/configure-roon-core.png)

### Step 3: Enable Roon extension
- Open Roon.
- Open the main menu, and select **Settings**.
- In the _Settings_ window, select **Extensions** and find the the **Elgato Stream Deck controller** extension.
- Click **Enable**.

> _Tip:_ You know you've entered the address and port correctly in Stream Deck once you see the button in Roon prompting you to enable the extension. If the extension doesn't show up, check the address you entered in Stream Deck, or try using your Roon Core's IP address, and click **Connect** again.

![Enable Roon extension](images/enable-roon-extension.png)

## Configure buttons
Once you've got the Roon Core configured and the extension enabled in Roon, you can start adding buttons and customizing them. You'll need to specify which Roon output each button should target. You can either type in the name of the zone/output, or you can select an active output from the _Available outputs_ dropdown. Only outputs active and connected to Roon will show up, but you can type in the name of inactive outputs at any time.

> Important: The name must match exactly what you've got in Roon.

![Output selection](images/output-selection.png)

> NOTE: If you have multiple outputs with the same name, the first one active at that point in time will be used. It is highly recommended to rename any duplicate outputs to be unique or your buttons may not control the output you intend!

### Settings
All actions have the option to _Dim when action not available_. This will cause the default button images to be dimmed slightly if that action is not available or Roon cannot be reached. Note, however, that this feature will not work if you customize the images for the button.

When you add a new button, it will be prepopulated with the previously selected output name. However, each button can target a different output. This means you can have one button control the music in the living room and another adjusting the kitchen.

## Troubleshooting
- *Nothing happens when I click _Connect_*: Verify that you've got the correct Roon address or IP and port, and that your computer can reach the Roon Core. You can try the following command to check connectivity: `curl -I \[my-roon-address]:9100/`. The port is random, so you may have to update it after a reboot or upgrade. You should see output similar to the following:
```
HTTP/1.1 404 Not Found
Content-Length: 0
```
- *Yeah, I get response that but it still doesn't work*: Make sure you've enabled the extension in Roon. You'll need to re-enable after uninstalling/reinstalling for example.
- *All the buttons are dimmed out*: Make sure you're still connected to Roon. Sometimes the auto-connect fails after network changes and such. Just hit **Connect...** in the button config
- *I get a warning image when I press a button*: This can happen if you try to start an invalid playlist, album, artist etc. or when there is no related content for the "Play related item" action. It will also happen if there's an error.

## Compatibility
Windows 10 and macOS 10.11+.

## Limitations
Only a single Roon Core can be used.

## Release notes

### [1.0.7] - 2020-08-07
- Fix issues when waking up from sleep where dynamically rendered images may cause buttons to fail to work.

### [1.0.6] - 2020-08-04
- Add ability to show current volume on volume set button

### [1.0.5] - 2020-06-27
* Fixed an issue causing the cover art to not always be rendered
* Fixed an issue causing the Play button to not update correctly
* Fixed issue where previous cover art was not removed if the next track didn't have cover art available
* Fixed an issue when adding buttons and the default zone wasn't set
* Added ability to reconnect to Roon Core by pressing any key when disconnected

## Misc
Roon is (probably) a trademark or registered trademark of Roon Labs LLC.

Elgato, Corsair, and Stream Deck are (probably) trademarks or registered trademarks of Corsair GmbH

Regardless, any trademarks, logos, and such are the property of their respective owners, so all you lawyers should focus on more important things.

