## Tue 02 May 2023

With the explosion of ChatGPT use, I decided to search around for a shell script that I could call from my terminal.
After testing out different ones, I settled on this one: https://github.com/0xacx/chatGPT-shell-cli

It's got some image generation capabilities that I do not use, but I left them there.

I have modified and edited the hell out of it for my own personal use.

The original script saved all previous prompts to a file `~/.chatgpt_history`. But I found that after a few weeks of use, that file grew quite large. Mine was over 2,000 lines when I made this revision.

It now creates a new daily file at `~/.chatgpt_history` with the format `Y-%m-%d.txt`.

I found this method better as I can now quickly "Live Grep" search with neovim 👍

Filename example: `~/.chat_history/2023-05-02.txt`.

When prompting the first prompt of the day, this is the output:

![image1](https://i.imgur.com/2NJRPuq.png)

Afterwards, this is the output:

![image2](https://i.imgur.com/zS6a3fc.png)

Each prompt is now also saved along with the response. I found this format to be easier to read.
![image3](https://i.imgur.com/plUgIco.png)

All prompt responses piped out to `xclip -selection clipboard`, so I can quickly and easily paste elsewhere.

---

## Usage:

First get your own API key from https://platform.openai.com/account/api-keys

And add these 2 lines to `.zshrc`.

`export OPENAI_API_KEY=sk-**********************************`

`export PATH="/home/UserName/path/to/script/chat:$PATH"`

Give your script the proper permissions.

`chmod +x chat`
