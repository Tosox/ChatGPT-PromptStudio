# <img src="assets/icon.png" height="40" /> ChatGPT PromptStudio

[![](https://img.shields.io/github/languages/code-size/Tosox/ChatGPT-PromptStudio?label=Code%20size&style=for-the-badge)](https://github.com/Tosox/ChatGPT-PromptStudio)
[![](https://tokei.rs/b1/github/Tosox/ChatGPT-PromptStudio?label=Total%20lines&style=for-the-badge)](https://github.com/Tosox/ChatGPT-PromptStudio)
[![](https://img.shields.io/github/downloads/Tosox/ChatGPT-PromptStudio/total?label=Downloads&style=for-the-badge)](https://github.com/Tosox/ChatGPT-PromptStudio/releases)

> [!NOTE]
> This project is intended for creative writing, storytelling and advanced prompt engineering. It does not encourage, promote, or condone the misuse of AI tools in violation of OpenAI's terms of service or ethical guidelines.  
> All example prompts and outputs are fictional and for illustrative purposes only.

## 📜 Description

ChatGPT PromptStudio is a Tampermonkey user script that allows users for creative writing, storytelling or advanced prompt engineering in ChatGPT. It fetches a long-form prompt from an external source and prepends it to your current input with a single click.

It comes with the following features:
* Prompt Injection Button – Adds a floating button to automatically prepend your custom prompt
* Remote Prompt Loading - Fetches and caches a prompt from a configurable online source
* Session Persistence – Uses local caching to avoid unnecessary re-downloads

## 🔧 Installation

1. Install the [Tampermonkey](https://www.tampermonkey.net/) browser extension
2. Go to the latest [ChatGPT-PromptStudio.user.js](https://github.com/Tosox/ChatGPT-PromptStudio/releases/latest/download/ChatGPT-PromptStudio.user.js) release
3. Press the `Install` button

## 🛠️ Customizing Your Prompt

ChatGPT PromptStudio fetches your prompt from a remote URL.

To use your own prompt:

1. Go to [https://gist.github.com](https://gist.github.com) or any other pastebin website
2. Create a new file and paste your desired prompt in plain text
3. Copy the raw URL (e.g. `https://gist.githubusercontent.com/yourusername/abc123/raw/filename.txt`)
4. Replace the `RAW_PROMPT_URL` value inside the script with your URL:
    ```javascript
    const RAW_PROMPT_URL = 'https://gist.githubusercontent.com/yourusername/abc123/raw/prompt.txt';
    ```
5. Save the script and refresh ChatGPT

### ⚠️ Important for new domains

If your prompt is hosted outside `gist.githubusercontent.com`, you must also add an @connect directive to the top of your script:
```
// @connect yourdomain.com
```

For example, if you're hosting the prompt at `https://pastebin.com/raw/...`, then add:

```
// @connect pastebin.com
```

This allows Tampermonkey to make network requests to that domain, bypassing browser security restrictions (CSP).

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
