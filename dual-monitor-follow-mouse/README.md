# A script to toggle Move filters depending on where your mouse is located.

> [!NOTE]
> Huge love to [@andilippi](https://github.com/andilippi) for his help on showing me how to create the C# method for capturing mouse movements. If you want really cool OBS widgets and stuff, I strongly suggest checking out his website https://streamup.tips/

## Prerequisites
- https://streamer.bot/
- https://obsproject.com/
- https://obsproject.com/forum/resources/move.913/

---

Quite a simple script, but it's a good example of how to use the Move filter in OBS and Streamerbot to have your monitor change depending on where your mouse is located.

### StreamerBot

```
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
```

### Tutorial

This is quite a simple version compared to my [ultrawide tutorial](/dual-monitor-follow-mouse/README.md) so I won't be doing a full deep dive, but how I currently have this set up is with a scene that contains sources for each monitor and it enables and disables them depending on where the mouse is with some animations handled via the Move filter.

### Script Breakdown

```csharp
CPH.ObsShowSource(scene, source, connection);
CPH.ObsHideSource(scene, source, connection);
```

`CPH.ObsShowSource` tells OBS to show the source inside the defined scene 
`CPH.ObsHideSource` tells OBS to hide the source inside the defined scene

So in my case with the script:

```csharp
// ...
CPH.ObsShowSource("Dual Monitor Switcher", "fakeMainScreen", 0);
CPH.ObsHideSource("Dual Monitor Switcher", "SubScreen", 0);
// ...
CPH.ObsHideSource("Dual Monitor Switcher", "fakeMainScreen", 0);
CPH.ObsShowSource("Dual Monitor Switcher", "SubScreen", 0);
// ...
```

So in my case, I'm telling the script that if the cursor is on the main monitor, show the `fakeMainScreen` source and hide the `SubScreen` source in the `Dual Monitor Switcher` scene. If the cursor is on the other monitor, hide the `fakeMainScreen` source and show the `SubScreen` source.
You could choose to handle this differently such as just completely changing scenes on change with something like `CPH.ObsSetScene(sceneName, connection);` instead, if you hate yourself and don't like to be clean with things lol.

### Screenshots of my setup

![alt text](/dual-monitor-follow-mouse/screenshots/1.png)

Both sources have a `Show` and `Hide` transition set up, moving to the left or right

![alt text](/dual-monitor-follow-mouse/screenshots/2.png)

---

## Why not check out my other projects?
Check out my [Doras](https://doras.to/tommerty) for everything I do!

![qrcode](https://github.com/tommerty/streamerbot-files/assets/86270372/2f028cb2-5c01-4e04-922d-4903a9940ce0)