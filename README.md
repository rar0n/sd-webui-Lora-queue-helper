# Hacky fork of Yinzo's sd-webui-Lora-queue-helper

Basically helpful to test different Lora's in one go (one lora at a time), like making a batch with a different lora in each generated picture.

### For using Loras via symbolic links (or not) on Automatic1111

Since I started using symbolic links for my SD stuff, this nice extension by Yinzo stopped working. But now it finally works again! At least on my Linux Mint system. Not tested on Windows or Mac.

I don't really know Python, so I enlisted some help from Claude 3.5 Sonnet.
Unfortunately, I used up the free limit (for now) and Claude wasn't quite finished with it... so I hacked together the rest. For now.

## Install
To install from webui, go to Extensions -> Install from URL, paste https://github.com/rar0n/sd-webui-Lora-queue-helper into the URL field, and press Install.
Then go to Extensions -> Installed tab, Press "Apply and restart UI".

## How to use
1. Locate the **Script** drop-down menu in the bottom left corner.
2. Select **Queue selected Loras (batch)** (Changed title from the original "Apply on every Lora")
3. Under **Select Directory** select the folders containing the Lora you want to use. Or click "All".
   + I **strongly** suggest to use **Use Custom Lora path** instead (Depending on your folder structure. My Lora folders are far too numerous to be useful without this)
       + Paste in your category folder path of Loras you want to use.
4. Select the **lora** you want to use (or click "All").
5. Generate.

#### Notes:

- It does **not** apply any negative prompt text (if present) in the Lora configuration file.
- I don't know how people normally structures their Lora collection (read tips below), me I have them in sub folder as categories somewhat structured after Civitai's Lora categories, although I changed it a bit. Then there's the Lora (sub) folders in each category which contains the actual Loras. This makes the "Select Directory" list very long as it currently is though. But that might just be me.
    + Ideally(?) I'd like the "Select Directory" list to only show Lora directories parent directories, and the Lora's still be listed under the Lora heading below. But for now this is it.

## Tips
+ Place your Lora into **sub-folders** by class (or categories, like "Vehicles", "Buildings", "Styles", etc).
+ Use built-in Lora configuration to store **Activation Text & Preferred Weight**, which will be automatically used in this script. Otherwise, it will only apply the Lora with default 1 weight.
