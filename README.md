#Make a Bot on Cloud9 using Hubot and Slack as an adapter
Hubot is an open-source bot written by GitHub in CoffeeScript and ran on Node.js. You can download scripts to customize your robot to your liking. Hubot can act as a help with translating languages, posting youtube videos, automating tasks, and much more.  You can learn more about Hubot here: https://hubot.github.com/
![](http://cdn0.icicletech.com/media/hubot.png)

##What You Will Need
To avoid downloading Node.js and npm, we will be using the Cloud9 IDE.
* cloud 9 account
* github account
* slack account

##What You Could Need
* spotify account (when creating your own custom hubot script to interact with spotify)
* youtube account

##Let's Get Started

###Login to Cloud9 and create a new workspace
Add a workspace name and choose node.js as a template

###We will be following the steps in Hubot's Getting Started Section 
Many of the steps taken below are from https://hubot.github.com/docs/ with a few added commands to make sure everything is up to date.

Make sure your npm version is up to date before generating hubot:

```% npm install -g npm```

Install a hubot generator

```% npm install -g yo generator-hubot```


Create a directory for your bot to reside in. The directory name should match your bot's name. I called my bot chattybot (but you could name it whatever you'd like)

```% mkdir chattybot```

```% cd chattybot```

```% yo hubot```

When you run the **yo** command you wil be asked a series of questions from a friendly bot.

The bot's name will be the same name as the one you made when you created a new directory.

When prompted, specify the adapter as **slack**. Here is an example below:

```? Owner Stephanie Marker <stephanie.marker93@gmail.com>```

```? Bot name chattybot```

```? Description A simple helpful robot for your Company```

```? Bot adapter slack```


###Let's add this to git and save our work

First, create a new repository. 

From the cloud9 terminal, let's push our work to our remote git repository.

``` % git init```

``` % git add .```

``` % git commit -m "Initial commit"```

``` % git remote add origin https://github.com/<your github username>/<your github repo name>.git```

``` % git push -u origin master```

When you refresh your github page, you should see your code pushed to your repo. Your chattybot is ready to get to work on slack, so now let's do some setup to add the bot to your slack chatroom.

Navigate to https://slack.com/signin

Click on **create a new team** on the top nav bar.

Answer all the questions, and then launch slack!

Click on **Team Settings**.

Click on **Configure Apps**.

Search **App Directory** for **Hubot**.

Click **Install**.

Name your bot chattybot and add the Hubot integration

You will get a hubot slack token to use for a hubot slack adapter. Use this token when you run your bot:

Run hubot:

```% HUBOT_SLACK_TOKEN=<token> ./bin/hubot --adapter slack``` 

When you return to slack you should see that your bot is online.

Click on **chattybot** and click on the little gear icon. 

You should be able to click on **Invite to a channel..** 

I picked the channel called **#random**. 

Now try typing in **chattybot time** into the #random channel. 

Chattybot should respond by giving you the server time!

###Add more functionality to chattybot through other npm packages
I installed a hubot-youtube package here https://github.com/hubot-scripts/hubot-youtube and followed its instructions.

Now you can write **chattybot youtube rick rolled** and get a link to a youtube url related to your search.

###Create your own chattybot scripts
See hubot-playspotify.js for an example with spotify
TODO: explain futher

###TODO: store env var for chattybot in redis




