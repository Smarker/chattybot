# Hubot Chatbot with Slack as an Adapter and the Spotify API

A custom chatbot built with github's [hubot](https://hubot.github.com/). 

The bot's name is chattybot and is customized to integrate with the Spotify API. The bot will respond to the basic chatbot commands:

```
chattybot help
```

and also respond to a custom command that draws from Spotify's API:

```
chattybot play <songname>
```

# Setting up the Bot

1. Clone this repo
2. Sign into Slack and create a team
3. Invite your bot to your team and a channel
4. Run this command to get your bot to listen on your channel:
```
HUBOT_SLACK_TOKEN=<your slack token> ./bin/hubot --adapter slack
```
5. In your channel, type chattybot ping to check that your bot responds