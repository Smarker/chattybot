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
  

#Let's Get Started

###Login to Cloud9 and create a new workspace
Add a workspace name and choose node.js as a template

##Create an instance of Hubot with Slack as an adapter

We will be following the steps in Hubot's Getting Started Section. Many of the steps taken below are from https://hubot.github.com/docs/ with a few added commands to make sure everything is up to date.

Make sure your npm version is up to date before generating hubot:

```% npm install -g npm```

Install a hubot generator

```% npm install -g yo generator-hubot```


Create a directory for your bot to reside in. The directory name should match your bot's name. I called my bot chattybot (but you could name it whatever you'd like)

```% mkdir chattybot```

```% cd chattybot```

```% yo hubot```

When you run the **yo** command you wil be asked a series of questions from a friendly bot. When prompted, specify the adapter as **slack**. Here is an example below:

```? Owner Stephanie Marker <stephanie.marker93@gmail.com>```

```? Bot name chattybot```

```? Description A simple helpful robot for your Company```

```? Bot adapter slack```


##Add Chattybot to Git

First, create a new repository. 

From the cloud9 terminal, let's push our work to our remote git repository.

``` % git init```

``` % git add .```

``` % git commit -m "Initial commit"```

``` % git remote add origin https://github.com/<your github username>/<your github repo name>.git```

``` % git push -u origin master```

When you refresh your github page, you should see your code pushed to your repo. Your chattybot is ready to get to work on slack, so now let's do some setup to add the bot to your slack chatroom.

##Add Hubot App to Slack

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

##Customize Chattybot
I looked around on npm and found a cool youtube package to add to Chattybot. I installed a hubot-youtube package here https://github.com/hubot-scripts/hubot-youtube and followed its instructions.

###Remember to restart Hubot to take your changes

Run Hubot.

```HUBOT_SLACK_TOKEN=<slack token> HUBOT_YOUTUBE_API_KEY=<youtube api key> ./bin/hubot --adapter slack```

Now you can write **chattybot youtube rick rolled** and get a link to a youtube url related to your search.

##Create your Own Chattybot scripts
Custom scrips may be written in either CoffeeScript or JavaScript.
See ```hubot-playspotify.js``` for an example of a custom script I made using the spotify api. 

This resource was really helpful when I was creating my script http://12devsofxmas.co.uk/2014/01/day-11-creating-your-own-franken-butler-with-hubot/ In particular, I thought it was good to know the difference between **hear** and **respond**

The article states that:
**hear** will listen to all messages sent and check whether the message matches the regular expression before executing the callback function

**respond** will only analyze the message if it is addressed directly to Chattybot (i.e. it starts with your hubot’s name)

TODO: make spotify credentials an env var

###TODO: store env var for chattybot in redis




