## Introduction

This is a simple Matrix bot that support using OpenAI API, Langchain to generate responses from user inputs. The bot responds to these commands: `!gpt`, `!chat`, `!v`, `!pic`, `!new`, `!lc` and `!help` depending on the first word of the prompt.
![ChatGPT](https://i.imgur.com/xP4bwMr.jpeg)

## Feature

1. Support official openai api and self host models([LocalAI](https://localai.io/model-compatibility/))
2. Support E2E Encrypted Room
3. Colorful code blocks
4. Langchain([Flowise](https://github.com/FlowiseAI/Flowise))
5. Image Generation with [DALL·E](https://platform.openai.com/docs/api-reference/images/create) or [LocalAI](https://localai.io/features/image-generation/) or [stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/API)
6. GPT Vision(openai or [GPT Vision API](https://platform.openai.com/docs/guides/vision) compatible such as [LocalAI](https://localai.io/features/gpt-vision/))
7. Room level and thread level chat context

## Installation and Setup

Docker method(Recommended):<br>
Edit `config.json` or `.env` with proper values <br>
For explainations and complete parameter list see: https://github.com/hibobmaster/matrix_chatgpt_bot/wiki <br>
Create two empty file, for persist database only<br>

```bash
touch sync_db context.db manage_db
sudo docker compose up -d
```
manage_db(can be ignored) is for langchain agent, sync_db is for matrix sync database, context.db is for bot chat context<br>
<hr>
Normal Method:<br>
system dependece: <code>libolm-dev</code>

1. Clone the repository and create virtual environment:

```
git clone https://github.com/hibobmaster/matrix_chatgpt_bot.git

python -m venv venv
source venv/bin/activate
```

2. Install the required dependencies:<br>

```
pip install -U pip setuptools wheel
pip install -r requirements.txt
```

3. Create a new config.json file and complete it with the necessary information:<br>
   If not set:<br>
   `room_id`: bot will work in the room where it is in <br>

```json
{
  "homeserver": "YOUR_HOMESERVER",
  "user_id": "YOUR_USER_ID",
  "password": "YOUR_PASSWORD",
  "device_id": "YOUR_DEVICE_ID",
  "room_id": "YOUR_ROOM_ID",
  "openai_api_key": "YOUR_API_KEY",
  "gpt_api_endpoint": "xxxxxxxxx"
}
```

4. Launch the bot:

```
python src/main.py
```

## Usage

To interact with the bot, simply send a message to the bot in the Matrix room with one of the following prompts:<br>
- `!help` help message

- `!gpt` To generate a one time response:

```
!gpt What is the meaning of life?
```

- `!chat` To chat using official api with context conversation

```
!chat Can you tell me a joke?
```

- GPT Vision command

You can refer the screenshot
```
Room Level: quote a image and @bot + {prompt}
Thread Level: quote a image with a {prompt}
```

- `!lc` To chat using langchain api endpoint
```
!lc All the world is a stage
```
- `!pic` To generate an image using openai DALL·E or LocalAI

```
!pic A bridal bouquet made of succulents
```
- `!agent` display or set langchain agent
```
!agent list
!agent use {agent_name}
```
- `!new + {chat}` Start a new converstaion

LangChain(flowise) admin: https://github.com/hibobmaster/matrix_chatgpt_bot/wiki/Langchain-(flowise)

## Image Generation
![demo1](https://i.imgur.com/voeomsF.jpg)
![demo2](https://i.imgur.com/BKZktWd.jpg)
https://github.com/hibobmaster/matrix_chatgpt_bot/wiki/ <br>

## GPT Vision
Room Level:
![GPT Vision Room Level](https://i.imgur.com/pUaxeps.jpeg)

Thread Level:

![GPT Vision Thread Level](https://i.imgur.com/Rw7wy3Y.jpeg)

## Thread level Context
Mention bot with prompt, bot will reply in thread.

To keep context just send prompt in thread directly without mention it.

![thread level context 1](https://i.imgur.com/4vLvNCt.jpeg)
![thread level context 2](https://i.imgur.com/1eb1Lmd.jpeg)


## Thanks
1. [matrix-nio](https://github.com/poljar/matrix-nio)
2. [acheong08](https://github.com/acheong08)
3. [8go](https://github.com/8go/)
