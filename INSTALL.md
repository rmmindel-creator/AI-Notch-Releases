# How to install AI Notch

This takes about 5 minutes. If you want the assistant too, give it another 10 for Ollama and the model download.

## 1. Download it

1. Go to the [Releases](../../releases) page.
2. Under the newest version, click the file that ends in **.dmg** to download it.

## 2. Install it

1. Open the .dmg file from your Downloads folder.
2. Drag **AI Notch** onto the **Applications** folder in the window that pops up.
3. Eject the disk image (the icon on your desktop or in Finder's sidebar). You can delete the .dmg after that.
4. Open **AI Notch** from your Applications folder or with Spotlight (⌘ Space, then type "AI Notch").

There's no Dock icon. AI Notch lives in the menu bar at the top of your screen, and the notch is where you use it.

### If macOS says it "can't be opened"

Early versions might not be signed by Apple yet, and macOS blocks apps it doesn't recognize. You only have to do this once:

1. Try to open AI Notch and click **Done** (or **OK**) on the warning.
2. Open **System Settings** → **Privacy & Security**.
3. Scroll down. You'll see a line saying AI Notch was blocked. Click **Open Anyway**.
4. Enter your Mac password if it asks, then click **Open Anyway** again.

## 3. Go through the welcome tutorial

The first time it opens, a short tutorial walks you through everything:

- **Pick a mode.** Notch, Assistant, or Both. You can switch later in Settings.
- **Try opening the notch.** Hover over it or click it, depending on what you choose.
- **Pick a keyboard shortcut** that opens the assistant from any app. Hold ⌘, ⌥ or ⌃ and press a key. You can change it or remove it later in Settings → Opening & Closing.
- **Connect the AI** (if you picked Assistant or Both). There's more on that below. You can skip this and come back to it.

Missed something? Click the AI Notch icon in the menu bar and choose **Show Tutorial…**

## 4. Allow the permissions

AI Notch only asks for what the features you turned on need. The easy way is **Settings → Permissions → Allow Everything**, then click Allow on each popup.

| Permission | What it's for |
|---|---|
| Accessibility | Showing volume and brightness in the notch, and letting the assistant see and click in other apps |
| Notifications | Timer alerts |
| Calendar and Reminders | Showing your schedule, and adding events and reminders when you ask |
| Contacts | Finding someone's email address |
| Location | Weather and "where am I" questions |
| Microphone and Speech Recognition | Talking to it instead of typing |
| Control other apps | Music, Spotify, Notes and Mail, when you ask it to |
| Full Disk Access | Showing when a Focus turns on or off (optional) |

**Accessibility is the one macOS won't pop up for you.** AI Notch opens the right page in System Settings. Find AI Notch in the list and switch it on. If it's already on but things still aren't working, switch it off and on again. That usually happens after updating the app.

## 5. Set up the assistant (optional)

Skip this if you only want the notch features.

The assistant uses [Ollama](https://ollama.com), a free app that runs AI models on your own hardware.

**Running it on the same Mac**

1. Download Ollama from [ollama.com/download](https://ollama.com/download) and install it like any other app. Open it once so it starts running.
2. Open Terminal and download a model. The model has to support tool calling so the assistant can actually do things. For example:
   ```
   ollama pull qwen3:8b
   ```
   It's a few GB, so it might take a while. If your Mac has 8 GB of memory, try a smaller model like `qwen3:4b`.
3. In AI Notch, go to **Settings → AI Model** (or the Connect step in the tutorial).
4. For the server, put `http://localhost:11434`.
5. Click **Test**. It shows the models it found. Pick the one you downloaded.

**Running it on another computer**

If you've got a beefier computer at home, you can run Ollama there and point AI Notch at it. Put that computer's address in the server box, like `http://192.168.1.50:11434`. You'll need to set Ollama up to accept connections from other devices on that machine. Their docs explain how.

## Updating

Download the newest .dmg from the Releases page and drag it into Applications again. Choose **Replace** when it asks. Your settings, tabs and files stay where they are.

## Uninstalling

1. Click the AI Notch icon in the menu bar and choose **Quit AI Notch**.
2. Drag AI Notch from Applications to the Trash.

If you want to get rid of its settings too, delete `~/Library/Preferences/com.ryanmindel.AI-Notch.plist`. To find it, open Finder, press ⌘⇧G and paste that path in.

## Something not working?

- **The notch doesn't open.** Make sure AI Notch is running (its icon should be in the menu bar). If you set it to hover, try clicking instead in Settings → Opening & Closing.
- **Volume and brightness still show the old gray box.** Accessibility isn't on. See step 4.
- **The assistant says it can't connect.** Make sure Ollama is open, then click Test in Settings → AI Model. If Ollama is on another computer, make sure both are on the same network.
- **The assistant is slow.** Try a smaller model. The first answer after a while is also slower because the model has to load.

Still stuck? Open an [issue](../../issues) and I'll take a look.
