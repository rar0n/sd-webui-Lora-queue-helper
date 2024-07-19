# Hacky fork of Yinzo's sd-webui-Lora-queue-helper

### For using Loras via symbolic links on Automatic1111

Basically helpful to test different Lora's in one go (one lora at a time), like making a batch with a different lora in each generated picture.

I don't really know Python, so I enlisted some help from Claude 3.5 Sonnet.
Unfortunately, I used up the free limit (for now) and Claude wasn't quite finished with it.. so I hacked together the rest. For now.
This should make the excellent extension by Yinzo work while using symbolic links to your Lora's, at least it does on my Linux Mint system. I haven't tested it on Windows.

#### A few tips / my use case
 + Tick "Use Custom Lora path", then paste in your category folder of Lora's you want to test.
    + (My Lora folders are far too numerous to be useful without "Use Custom Lora path")
 + If you have hard drive space limitations, use symbolic links to folders on other drives (Preferably a fast M2.nvme drive...)
   + Then you can also easily-ish add or remove said links, to isolate Automatic1111'a access to SD1.5, SD2.1 or SDXL stuff (models) for further batch operations

#### Todo, or wish-list:

- I think it would be better if the "Select Directory" list did not include the final sub-directory where the Lora(s) are. They will be included in the Lora Selection list below anyway, so this only makes the list (way) longer.
- Conversely, the "Select Directory" list does not need the root folder ("/") to be listed either.
- I do not think it applies the negative text (if present) in the Lora configuration file.
- General clean up and make it less hacky

Ofc, I don't know how people normally structures their Lora collection (read tips below), me I have them in sub folder as categories somewhat structured after Civitai's Lora categories, although I changed it a bit (Like "Backgrounds - environments - landscapes" collated into one folder, "Characters", "Styles - concepts", "Vehicles", and other folders). Then there's subfolders in each category which again contains the Lora. This makes the "Select Directory" list very long though.  But that might just be me.
However, ever since I started using symbolic links for my SD stuff, this nice extension by Yinzo didn't work. But not it does! (I hope).

### Slightly edited instructions below:

# Lora Queue Helper for SD WebUI A1111

A script that helps you generate a batch of Lora, using the same prompt & settings.

Helpful to compare Lora for the same character with identical prompt & settings / Generate different characters from the same source (like the sample picture) / Or just switch and pick Lora easily without changing the tab.


![](https://raw.githubusercontent.com/Yinzo/sd-webui-Lora-queue-helper/main/docs/ui.png)
![](https://raw.githubusercontent.com/Yinzo/sd-webui-Lora-queue-helper/main/docs/output_sample.png)

## Install
To install from webui, go to Extensions -> Install from URL, paste https://github.com/rar0n/sd-webui-Lora-queue-helper into the URL field, and press Install.

## How to use
1. Locate the **Script** menu in the bottom left corner.
2. Select **"Apply every Lora"** (Slightly changed title from the original)
3. Select the **folder** that contains the Lora you want to use.
4. Select the **lora** you want to use.
5. Generate.

## Tips
+ Place your Lora into **sub-folders** by class.
+ Use built-in Lora configuration to store **Activation Text & Preferred Weight**, which will be automatically used in this script. Otherwise, it will only apply the Lora with default 1 weight.
