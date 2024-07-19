# Hacky fork of Yinzo's sd-webui-Lora-queue-helper

Basically helpful to test different Lora's in one go (one lora at a time), like making a batch with a different lora in each generated picture.

### For using Loras via symbolic links on Automatic1111

Since I started using symbolic links for my SD stuff, this nice extension by Yinzo didn't work. But now it does! At least on my Linux Mint system. Not tested on Windows or Mac.

I don't really know Python, so I enlisted some help from Claude 3.5 Sonnet.
Unfortunately, I used up the free limit (for now) and Claude wasn't quite finished with it... so I hacked together the rest. For now.
This should make the excellent extension by Yinzo work while using symbolic links to your Lora's.

#### Usage tip (also see Tips below)
 + Tick **Use Custom Lora path**, then paste in your category folder path of Lora's you want to test.
    + (My Lora folders are far too numerous to be useful without "Use Custom Lora path", as in the below tip #3)
 + Under **Select Directory** click "All", or just the folders you want.
 + Then under **Lora** select the Loras you want (or click "All").
 + The Loras will now be applied one by one in the prompt, which is otherwise the same in each image.
 + **This extension only works for Lora's** (and now also via symbolic links).

#### Todo, or wish-list:

- It does **not** apply any negative prompt text (if present) in the Lora configuration file.
- I'd like the "Select Directory" list to only show Lora directories parent directories, as the Lora's should then still be listed under the Lora heading below.
  + I don't know how people normally structures their Lora collection (read tips below), me I have them in sub folder as categories somewhat structured after Civitai's Lora categories, although I changed it a bit. Then there's the Lora (sub) folders in each category which contains the actual Loras. This makes the "Select Directory" list very long as it currently is though. But that might just be me.
- Some clean up and make it less hacky?

### Original instructions below, slightly edited for this fork

# Lora Queue Helper for SD WebUI A1111

A script that helps you generate a batch of Lora, using the same prompt & settings.

Helpful to compare Lora for the same character with identical prompt & settings / Generate different characters from the same source (like the sample picture) / Or just switch and pick Lora easily without changing the tab.


![](https://raw.githubusercontent.com/Yinzo/sd-webui-Lora-queue-helper/main/docs/ui.png)
![](https://raw.githubusercontent.com/Yinzo/sd-webui-Lora-queue-helper/main/docs/output_sample.png)

## Install
To install from webui, go to Extensions -> Install from URL, paste https://github.com/rar0n/sd-webui-Lora-queue-helper into the URL field, and press Install.
Then go to Extensions -> Installed tab, Press "Apply and restart UI".

## How to use
1. Locate the **Script** drop-down menu in the bottom left corner.
2. Select **Queue selected Loras (batch)** (Changed title from the original "Apply on every Lora")
3. Select the **folder** that contains the Lora you want to use. (I suggest to use **Use Custom Lora path** instead, depending on your folder structure)
4. Select the **lora** you want to use.
5. Generate.

## Tips
+ Place your Lora into **sub-folders** by class.
+ Use built-in Lora configuration to store **Activation Text & Preferred Weight**, which will be automatically used in this script. Otherwise, it will only apply the Lora with default 1 weight.
