# A script to toggle Move filters depending on where your mouse is located.

> [!NOTE]
> Huge love to [@andilippi](https://github.com/andilippi) for his help on showing me how to create the C# method for capturing mouse movements. If you want really cool OBS widgets and stuff, I strongly suggest checking out his website https://streamup.tips/

## Prerequisites
- https://streamer.bot/
- https://obsproject.com/
- https://obsproject.com/forum/resources/move.913/

---

### OBS Setup

1. Launch OBS and create a scene that has your monitor source, and stretch it out so it's aligned with the top, bottom, and left of your screen.
![image](https://github.com/tommerty/streamerbot-files/assets/86270372/3d9ae433-4a08-4bc3-b00f-b6cf988520cf)
2. Right click on the `source` (not your display capture) and go to `filters`
3. Create a `Move Source` filter and call it `Left`.
4. Ensure the `Source` is set to your display capture and scroll down and click `Get Transform`.
5. Create a `Move Source` filter and call it `Right`.
6. Drag your display capture over to the right of the screen, and then inside your `Right` filter, click `Get Transform`.
7. (Optional) Create a third filter called `Center`, and resize your monitor to fit on the `X` of the screen, leaving black bars at the top and bottom. Then click `Get Transform` again.
I mainly use this if I don't want it to follow my mouse and just showcase the entire screen.

After this you should be left with something like this:

https://github.com/tommerty/streamerbot-files/assets/86270372/8ea92fab-ab08-4c77-bec8-1f546004d76b

---

### StreamerBot

1. Download the import file [here]().
2. Launch StreamerBot and click `Import`, and drag the file into the `Import String` section.
#### Breakdown of the Actions
- StreamUP Tools Get Cursor Position:
  - This is the main script that runs every second to check for the cursor position on your screen and sets the filter
- Disable Follow Mouse
  - Simple action to disable the timer and sets the `Center` filter (if you followed that optional step)
- Enable Follow Mouse
  - Simple action to re-enable the timer. (The reason I split these two up was so I could create a simple toggle on my Streamdeck, but you can modify these to your liking of course)

3. Click the `StreamUP Tools Get Cursor Position` Action and click into the `Execute Code` Sub-Action
4. I currently have it doing if the mouse is in the first 2000px, use the `Left` filter, otherwise use the `Right` filter, though this could be adjusted. If you have 3440px on your X axis for example (standard ultrawide pixel ratio) and want to split it 50/50, you could do something like `if (cursor.X < 1720)` instead! I mostly use the left side, so decided to give it a bigger buffer.
5. As you can see it says `CPH.ObsShowFilter("MainScreen", "Left", 0);`, you'll need to modify this for your own use case.
Where it says `MainScreen` this would be the scene, and `Left` being the name of the filter on that scene.
For a more detailed breakdown on how it works, check out [this section](https://docs.streamer.bot/api/csharp/obs/filters#ObsShowFilter) on the StreamerBot docs.
6. Once you've done that, click `Save & Compile`, and ensure the Timed Action is enabled. You can do that by right clicking on it and click enabled.

You should now see something like this:

https://github.com/tommerty/streamerbot-files/assets/86270372/171450de-95b9-41b1-b3c9-e28ce9ca96a1

---

### Optional - Streamdeck

So you likely don't always want this enabled, so that's why there was the optional steps of creating the `Center` filter.

For this we'll need Streamdeck and StreamerBot setup together. Get started following this: https://streamdeck.streamer.bot/

1. Head over to your StreamDeck app and create a new button for `Action Switch`.
2. For the `Toggle On` set `Disable Follow Mouse`
3. For the `Toggle Off` set `Enable Follow Mouse`

It should then work like this:

https://github.com/tommerty/streamerbot-files/assets/86270372/cd7330e6-c784-4946-8088-1a8a005e5b83

