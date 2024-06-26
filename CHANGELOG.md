# Changelog

## 1.8.0
- Support custom help message

Create a `custom_help_message.txt` and uncomment the field in docker compose file.
![Imgur](https://i.imgur.com/X5vGr6v.jpeg)
- Support several whitelist room_id

You can add as many as room_id that you hope the bot works on.

`"room_id": ["!111111:matrix.qqs.tw", "!222222:matrix.qqs.tw"]` for `config.json`

`ROOM_ID="!aaaaaaa:XXX.XXX,!bbbbbb:XXX.XXX"` for `.env`

## 1.7.2
- Refactor gpt vision trigger method
- !pic, !help, and gpt vision in thread chat
- Add GPT Vision thread level response to context

## 1.7.1
- Fix official openai image generation
- Thread level chatting for Element Android

## 1.7.0
- Support thread level context

## 1.6.0
- Add GPT Vision

## 1.5.3
- Make gptbot more compatible by using non-streaming method

## 1.5.2
- Expose more stable diffusion webui api parameters

## 1.5.1
- fix: set timeout not work in image generation

## 1.5.0
- Fix localai v2.0+ image generation
- Fallback to gpt-3.5-turbo when caculate tokens using custom model

## 1.4.1
- Fix variable type imported from environment variable
- Bump pre-commit hook version

## 1.4.0
- Fix access_token login method not work in E2EE Room

## 1.3.0
- remove support for bing,bard,pandora
- refactor chat logic, add self host model support
- support new image generation endpoint
- admin system to manage langchain(flowise backend)

## 1.2.0
- rename `api_key` to `openai_api_key` in `config.json`
- rename `bing_api_endpoint` to `api_endpoint` in `config.json` and `env` file
- add `temperature` option to control ChatGPT model temperature
- remove `jailbreakEnabled` option
- session isolation for `!chat`, `!bing`, `!bard` command
- `!new + {chat,bing,bard,talk}` now can be used to create new conversation
- send some error message to user
- bug fix and code cleanup
