# Symlink fork of Yinzo's sd-webui-Lora-queue-helper

## For using Loras via symbolic links on Automatic1111

Basically helpful to test different Lora's in one go (one lora at a time), like making a batch with a different lora in each generated picture.

Since I started using symbolic links for my SD stuff, this nice extension by Yinzo stopped working. But now it finally works again! At least on my Linux Mint system. Not tested on Windows or Mac.

I don't really know Python, so I enlisted some help from Claude 3.5 Sonnet.
Unfortunately, I used up the free limit (for now) and Claude wasn't quite finished with it... so I hacked together the rest. Seems to work.

### Bugs

 - Apparently Lora's that Automatic1111 for some reason or another can't find (despite it being in the correct place and path), or can't use, is retried twice somehow. But the image is generated without it (getting "Lora not found" if you try it with only one such Lora). So, I'm not sure what's up with all this, but otherwise it seems to work. I think :)


## Install
To install from webui, go to Extensions -> Install from URL, paste https://github.com/rar0n/sd-webui-Lora-queue-helper into the URL field, and press Install.
Then go to Extensions -> Installed tab, Press "Apply and restart UI".

## How to use
1. Locate the **Script** drop-down menu in the bottom left corner of Automatic1111 web UI
2. Select **Queue selected Loras (batch)** (Changed title from the original "Apply on every Lora")
3. Under **Select Directory** select the folders containing the Lora you want to use (Or click **All**)
   + I suggest to use **Use Custom Lora path** (Depending on your folder structure and amount of Loras)
       + Paste in your folder path of the category of Lora(s) you want to test / use
4. Under **Lora** select the Lora's you want to test (or click **All**)
   + At least one Lora folder has to be selected first for the Lora section to show up
   + If you've got a lot of folders, you have to scroll down past the **Select Directory** section end to reach it
5. **Generate!**

## Tips

- Place your Lora into **sub-folders** by category (like "Vehicles", "Buildings", "Styles" or some such)
- Use built-in Lora configuration to store **Activation Text & Preferred Weight**, which will be automatically used in this script. Otherwise, it will only apply the Lora with default 1 weight 
- It does **not** apply any negative prompt text (if present) in the Lora configuration file

Ideally(?) I'd like the "Select Directory" list to only show the parent folder of the Lora folders, and the Loras still be listed under the Lora heading below. But for now and the foreseeable future, this is it (Most people seem to have moved on to ComfyUI or Forge anyway. This might still work with Forge btw, not tested).
