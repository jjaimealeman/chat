## May 02 2023 _(date started)_
## Aug 26 2023 _(date modified)_

**CREDIT FOR THE ORIGINAL SCRIPT GOES TO** https://github.com/0xacx/chatGPT-shell-cli

With the explosion of ChatGPT use, I decided to search around for a shell script that I could call from my terminal.
After testing out different ones, I settled on this one.

I have modified and edited the hell out of it for my own personal use. It's got some image generation capabilities that I do not use often.

## My Edits:

The original script saved all previous prompts to a file `~/.chatgpt_history`. But I found that after a few weeks of use, that file grew quite large. Mine was over 2,000 lines when I made this modification. It now creates a new daily file at `~/.chatgpt_history` with the format `Y-%m-%d.md`.

Filename examples:
```
~/.chat_history/2023-08-24.md
~/.chat_history/2023-08-25.md
~/.chat_history/2023-08-26.md
```

I found this method better as I can now quickly "Live Grep" search with Neovim 👍

---

When prompting the first prompt of the day, this was the old output:

![image1](https://i.imgur.com/2NJRPuq.png)

I made it so that it shows the current date file, and the number of prompts & lines for the day:

![image2](https://i.imgur.com/9FzJMP2.png)

---

Each prompt is now also now saved for better readability.
![image3](https://i.imgur.com/plUgIco.png)

---

I heavily use [rofi](https://github.com/davatorium/rofi) _(A window switcher, application launcher and dmenu replacement )_ with [greenclip](https://github.com/erebe/greenclip) _(Simple clipboard manager to be integrated with rofi)_.

So I made all prompt responses piped out to `xclip -selection clipboard`, so I can quickly and easily paste elsewhere.

Generated images are saved to `~/.chatgpt_history/images` folder with date stamp, and suffixed with an incrementing number count.

Filename examples:
```
~/.chat_history/images/2023-08-26_1.png
~/.chat_history/images/2023-08-26_2.png
~/.chat_history/images/2023-08-26_3.png
```

---

## Usage:

First get your own API key from https://platform.openai.com/account/api-keys

And add these 2 lines to `.zshrc`.

`export OPENAI_API_KEY=sk-**********************************`

`export PATH="/home/UserName/path/to/script/chat:$PATH"`

Give your script the proper permissions.

`chmod +x chat`

## Requirements:
```
curl (for API calls)
jq (JSON parser)
xclip (clipboard)
glow (markdown viewer)
```

## Video:

https://github.com/jjaimealeman/chat/assets/1428292/c2004064-7a09-499a-8d8a-c8d7406f68f8

## DALL-E generated image:

![2023-08-26_10](https://github.com/jjaimealeman/chat/assets/1428292/b441f9c5-885a-478b-91d3-3167356289f2)
