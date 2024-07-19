# Hacky fork of Yinzo's sd-webui-Lora-queue-helper

Basically helpful to test different Lora's in one go (one lora at a time), like making a batch with a different lora in each generated picture.

### For using Loras via symbolic links on Automatic1111

Since I started using symbolic links for my SD stuff, this nice extension by Yinzo didn't work. But now it does! At least on my Linux Mint system. Not tested on Windows or Mac.

I don't really know Python, so I enlisted some help from Claude 3.5 Sonnet.
Unfortunately, I used up the free limit (for now) and Claude wasn't quite finished with it... so I hacked together the rest. For now.
This should make the excellent extension by Yinzo work while using symbolic links to your Lora's.

#### A few tips / my use case
 + Tick **Use Custom Lora path**, then paste in your category folder of Lora's you want to test.
    + (My Lora folders are far too numerous to be useful without "Use Custom Lora path", as in the below tip #3)
 + Automatic1111 follows any subfolders / sub directories that you make within its different resource folders, like for Lora's. And also symbolic links. So you can have it organized.
   + Using symlinks you can easily-ish add or remove said links (easier if using a script), to isolate Automatic1111'a access to SD1.5, SD2.1 or SDXL stuff (models) for ease of further batch operations. For example adding only one type of SD models with "X/Y/Z plot" and "Checkpoint name" (say only SDXL, or only SD1.5).
   + If you have hard drive space limitations, use symbolic links to folders on other drives (Preferably a fast M2.nvme drive). There needs to be a symbolic link from each of Automatic1111's appropriate folders (Lora folder, Embeddings folder, Models folder, VAE, what have you).
 + **This extension only works for Lora's (and now also if using symbolic links)**.

#### Todo, or wish-list:

- I think it would be better if the **Select Directory** list did not include the final sub-directories where the Lora(s) are. They will be included in the **Lora** Selection list below anyway (or at least they should be), so this only makes the list (way) longer.
  + In short I think "Select Directory" list should only contain the parent directories of Lora directories.
- Conversely, the "Select Directory" list does not need the root folder ("/") to be listed either, but this is a very minor thing.
- I do not think it applies the negative text (if present) in the Lora configuration file.
- Sometimes some errors pop up in the console, other times (mostly?) not. Not sure what's up with that.
- General clean up and make it less hacky

I don't know how people normally structures their Lora collection (read tips below), me I have them in sub folder as categories somewhat structured after Civitai's Lora categories, although I changed it a bit. Then there's actual Lora (sub) folders in each category which contains the Loras. This makes the "Select Directory" list very long as it currently is though. But that might just be me.

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
2. Select **"Solo apply selected Loras batch"** (Changed title from the original "Apply on every Lora")
3. Select the **folder** that contains the Lora you want to use. (I suggest to use **Use Custom Lora path** instead, depending on your folder structure)
4. Select the **lora** you want to use.
5. Generate.

## Tips
+ Place your Lora into **sub-folders** by class.
+ Use built-in Lora configuration to store **Activation Text & Preferred Weight**, which will be automatically used in this script. Otherwise, it will only apply the Lora with default 1 weight.
