## Tue 02 May 2023

With the explosion of ChatGPT use, I decided to search around for a shell script that I could call from my terminal.
After testing out different ones, I settled on this one: https://github.com/0xacx/chatGPT-shell-cli

I have modified and edited the hell out of it for my own personal use.

---

First get your own API key from https://platform.openai.com/account/api-keys

And add these 2 lines to `.zshrc`.

`export OPENAI_API_KEY=sk-**********************************`

`export PATH="/home/UserName/path/to/script/chat:$PATH"`

Give your script the proper permissions.

`chmod +x chat`
