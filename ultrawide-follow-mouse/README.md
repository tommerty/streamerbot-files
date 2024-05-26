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

1. Copy/paste the import string
```
U0JBRR+LCAAAAAAABADtWMty4lgS3XdE/wPhxcym5dATpIqYhYVtIVzQZTAINNTiviRkXz1aD7DcURHzLfNp/SWdEk+Bqemp6e6ZxRChQGTmzZt5TuZVip+//67VulqxNAvi6OpDS/mhFgRhEqf59FQcBlEQFuFBfiVey9fK1VbLcgSyn6sf8DNCIatMJjxP0TqgrHUfcx6vW4O4yNhmDZihIl/GaWX4FIchS/NyrzqEdSVdi9fiXkFZRtIgybfKY1/xqIhuyFYTFZxXqi+bAClqBIhqswwkf99IWjtVrQ5o5VuRNIRJGwuKzjRBpZos6BLzBCRTgxiSorWNfS71sp8KVrDt3sdyFiHMWeUzTwvW0LwSXlB2n8ZhL8jyOC3fMdqhOc5ThsLJp9ZTHPOs9cs//tmyWN7qFmkWp61PcRbUuR8v9dO4SKq1DeA3EPA1KjOA7J0dUxTRONxj6SGeNfQkjkiRpizK39PmaeD7wN8xuicIb+wC4NyuoWZtXeu0O20BYyQKqkeIgNuiJyiMyIh1OkZbJMfRH7HEDJXpEmGC3lEMQdUMVTBUxARDJ6KnyVjWRflsaV4mFaQdUTrVHLg6zetAWLarnc/H2i+HH58bQJ/X2nto7FiuKCUbSpN3KK1tT5oAlvw1a+VL1nptAXOtcr+yFXu1fOPww/Z71vrL9m5+5jplHgNiCTsLuFZ3PywWTgDVsc4Wi0FA0jiLvfx6ePe0WNynkMI6Tl8Wi5UKTauIimQsFmFG4pQH+Jpyfrrdt3kcl1nOwuvb6myJ/Npv0+3n06xwmbNuTGuA6WyY4JD4E4W/UWua/7gWH05lH19G5XxGK1nn9jGRiMwLtzSf2Gwouo5YTKJpQS2eu2Otj6MRJ6GxnsjTkob82Z0NYE087EamNA9fk3lpPmPr/o2U5u3kbtnHIMPhBPTZsBvc+HbXxCPrNRs70horffGh24f9puXgzS5ckNsBp+AP7G58ooyWsO+zbU1ViLPEgRlg2cjsO8rp3VAi0XBFuLki5bJ0nbk/sYwER48+7pmPGHKg3ZfO3ldvGuDaV3+F5bU/mi35XJmK7thPdjYMsKm+N9fOh/lMZ/03rNj+p7FZuDOy2yd+eNrltLlG8lR8VKYlkY0SbN4een3uBvv1yY8N/zerj6XZB72GlYlPwnsRQY62dee7Fg/dcAo5aaJtDSWIYeWGc//Bek2QPPHn4xtp0NXhesnsHl/Rsfk8d1QfO8YLclzN7o1iNBv4NLzPqDMpdvltLn1l391nRNZ9at2n7tiEXEYr29JW1Jr4zDEkEpg5lrWEWkYJPJbubLjCvamIHKP4GJhWhYU7Wy7xzMxgfc7GB3vb4m/27UAc3pprBnEDZ5AX+O2u/bM4ekPYl4e2JWlwraAueb3e4kWVA/gOEWBHuzfl4PZmTXp+BjrR7kGtWmu/tq/tboInaxrSLsQV8qyqlcZe1R7d5Y6Hwune6PatvQafScOu1+TzgNe21gIzATySXU643rO656VbcbSVE3kI3E1PcN9zDnia2dyB2Lv94dzhxWRrbwemgmajeJv721yeFu547c8d7QVsB67jiic2xdyRADMjrOtgdiH/TT1DP/rFk9x/m8jLFRXdBPeglwM/eHLuE8yHzyScchzY2WGvtT846qENRmIDI9d5fXMfG33TuZD37a6PqtpEUK/UWgJ//cSVl+KmZvsvm1y2+SvQP476PifQW8R6Xc6hH+wXaYkc7WlrH1T1QS1/63/4DH3EP3bNJQ4ffZtv9/tzcBwjh8ZQl5kNtdbsf9Ooz82j3D6WhtHEus9prz73RBJN+X59xUEk/u3scZakjMRhEnB26YlOGUflOEfpe7NMbZGhFRuxrOD5UzxFaVANCF+zbVhdXRhbOpqIOqIhCx0V6YKqerqgM0URZOoRqsuep0re2dI1C/xlFSdMxBdGGqP6nOr2Y+CZx4uj6SbUiLLXarvfPudY1Vab4ag5MXKOkozRI/1O/WVveD6DixgrGvbagoIwDIaKoQm6LCFBUnSkwYlNCfX+iBn8bKjdjWd3tZ9332eaUH994j7z//uN3N8yfP6no3iWo7yC56wqtyzKkoY1qgqSrMGM3saKYCANCxrIDNXTsK6d+/wNxa5fKvQT9r9eAZtA/+ulboiGB/DogkQ7MpwIYltAtIMEvS3KhFEFK0T6U0v9Nsj+X+uXa/3s1XFDo6yKniLqDDwpKtDY0QSEGRM0RpjmiYony/h/stZ/+BpoGWERG24LY4CCaExSxs7fTL2A5yzdGXaBQpZeRFA+VQDxEatZ3PJDVVlFIhEY0xVBpe0OvOVjeFxSXUfIk1TZkC48X1XN0ESpjSoGJEHVO7oAJ44qGMxoa4gaskfa30KD2vn9eZD+2DNnc7Oz3xwbDRewPAyhJ5vCNcNZTF5YPmbp6qTfDsouD4DkprLusH/x59q/23qHBzDEUrbGMNZFtGFw+Z+bq5QlDOXvHIhBVZ8rxE/aeXtC2QftmcsiSeAUORgc18sVD6IaYbHJUVF3w1Hf7aip/6j8/rsvvwKgO+CikxUAAA==
```
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

---

## Why not check out my other projects?
Check out my [Doras](https://doras.to/tommerty) for everything I do!

![qrcode (1)](https://github.com/tommerty/streamerbot-files/assets/86270372/2f028cb2-5c01-4e04-922d-4903a9940ce0)

