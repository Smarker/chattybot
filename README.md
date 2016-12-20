#Make a Slack Chatbot on Cloud9 using Hubot
![](http://i.markdownnotes.com/blob_DrFpIes)

Hubot is an open-source chatbot written by GitHub in CoffeeScript and is ran on Node.js. You can download scripts to customize your robot to your liking. You can learn more about Hubot here: https://hubot.github.com/


##What You Need
To avoid downloading Node.js and npm, we will be using the Cloud9 IDE.
* cloud 9 account
* github account
* slack account

##Let's Get Started

###Login to Cloud9 and create a new workspace
Add a workspace name and choose node.js as a template

![](http://i.markdownnotes.com/blob_nJXalgp)

###We will be following the steps in Hubot's Getting Started Section 
Many of the steps taken below are from https://hubot.github.com/docs/ with a few added commands to make sure everything is up to date.

Make sure your npm version is up to date before generating hubot:
```% npm install -g npm```

Install a hubot generator
```% npm install -g yo generator-hubot```


Make a bot called chattybot (or whatever name you'd like)
```% mkdir chattybot```
```% cd chattybot```
```% yo hubot```

When you run the **yo** command you wil be asked a series of questions from this friendly bot:
![](http://i.markdownnotes.com/blob_myQqyl0)

The bot's name will be the same name as the one you made when you created a new directory.

When prompted, specify the adapter as **slack**. Here is an example below:
```? Owner Stephanie Marker <stephanie.marker93@gmail.com>```
```? Bot name chattybot```
```? Description A simple helpful robot for your Company```
```? Bot adapter slack```


###Let's add this to git and save our work

First, create a new repository:

![](http://i.markdownnotes.com/blob_ibvNspv)

From the cloud9 terminal, let's push our work to our remote git repository.
``` % git init```
``` % git add .```
``` % git commit -m "Initial commit"```
``` % git remote add origin https://github.com/<your github username>/<your github repo name>.git```
``` % git push -u origin master```

When you refresh your github page, you should see your code pushed to your repo. Your chattybot is ready to get to work on slack, so now let's do some setup to add the bot to your slack chatroom.

Navigate to https://slack.com/signin
Click on **create a new team** on the top nav bar.

![](http://i.markdownnotes.com/blob_3Chk9GD)
Answer all the questions, and then launch slack!

Click on **Team Settings**:
![](http://i.markdownnotes.com/blob_67NX5EM)

Click on **Configure Apps**:
![](http://i.markdownnotes.com/blob_roWsiFV)

Search **App Directory** for **Hubot**
![](http://i.markdownnotes.com/blob_NS2vKVF.jpg)

Click **Install**:
![](http://i.markdownnotes.com/blob_JiHBeVK.jpg)
Name your bot chattybot and add the Hubot integration

You will get a hubot slack token to use for a hubot slack adapter.
In cloud9 export the slack token:
```export HUBOT_SLACK_TOKEN=<token>```

Run hubot:
```% ./bin/hubot --adapter slack``` 

When you return to slack you should see that your bot is online:
![](http://i.markdownnotes.com/blob_lvOX9oB)

Click on **chattybot** and click on the little gear icon. You should be able to click on **Invite to a channel..** I picked the channel called **#random**. Now try typing in **chattybot time** into the #random channel. Chattybot should respond by giving you the server time!





