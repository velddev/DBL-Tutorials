# Getting started with your first discord bot
Hello, and today I’m showing you how to write and set up a Discord bot in discord.py. This tutorial will be friendly for programmers of any level as long as you know your basics in any language, if you feel a little 
## Why Discord.py?
The reason I picked discord.py over Disco is mainly the community, Disco is a bit tougher to get support for. Another reason is that discord.py is a lot more mature at this moment.
## Requirements
Alright, let’s go over our requirements really quick. There are a small number of things we might need. And we will go over most of the possibilities as best as I can.
A discord token
First, we need a bot to connect to. This can be done by going to the [developer page (click me)](https://discordapp.com/developers/applications/me) of discord. Click the link, and we will go 
 
 ![](https://i.imgur.com/V19wk5w.png)
 
 ![](https://i.imgur.com/qtctRTL.png)
 
 ![](https://i.imgur.com/Am6ZvfK.png)
 
Now, scroll slightly down, and press this button. This button will create a bot user with a user ID and a bot token, those can be used to either create an invite to your bot or to log in to your bot with the API!
 
 ![](https://i.imgur.com/9R6YAPs.png)
 
Now, that you have a bot user, press the reveal token. Keep this somewhere safe because this is your bot’s very own discord password!
Now lets invite our bot to a discord server!
https://discordapp.com/oauth2/authorize?&client_id= YOUR CLIENT ID &scope=bot
if everything went wel, it should look like this
 
 ![](https://i.imgur.com/KQ1kfY2.png)
 
Pick the server you so desire the bot to be on, and press Authorize. This will automatically add the bot to your guild 

![](https://i.imgur.com/GrJnUut.png)

## Python
Of course, to start it off, we need Python. ( https://www.python.org/downloads/release/python-364/ ) Simply download the one you need Windows or Mac links will be available here, for Linux distributions, check the website. Listed here
If you’re completely new to python, you might want to get a refresher as well. I recommend reading through http://www.pythonforbeginners.com/. It is a very well-structured source for beginners.
##An editor, or IDE
There are a handful of editors available for Python, but for now I’d recommend going with PyCharm, as the tutorial will work with that.
https://www.jetbrains.com/pycharm/

![](https://i.imgur.com/xSAHcQo.png)
![](https://i.imgur.com/occi4hU.png)
![](https://i.imgur.com/1eVLDCb.png)
![](https://i.imgur.com/w4l3Ksc.png)
![](https://i.imgur.com/SmABPOw.png)
![](https://i.imgur.com/AfcNLZR.png)
![](https://i.imgur.com/ctwUNTp.png)
![](https://i.imgur.com/dHIUTz4.png)
![](https://i.imgur.com/ulpzvmW.png)
![](https://i.imgur.com/zXd4g4n.png)

-- we're ready
       
```
print(“Hello World!”)
```

![](https://i.imgur.com/dHIUTz4.png)
![](https://i.imgur.com/ulpzvmW.png)
![](https://i.imgur.com/zXd4g4n.png)
![](https://i.imgur.com/RBDwiW4.png)

Now that our set up is done, lets dig in the code. First we want to make a client to connect to the discord API, we can do this with the following code:

```py
import discord

client = discord.Client()

@client.event
async def on_ready():
    print(‘Hello World, signing in from {}’.format(client.user.name))

client.run('my token here!')
```

Alright, lets test what we got so far! Run the bot and if everything went as planned, you should see this appear in your command line!
 
![](https://i.imgur.com/HPY2WJG.png)
 
Next up, we should probably get some sort of message handler, for that we can make another client.event, for messages this time!
With this message event, we will make it respond to the line “Hello”. So we want a check to see if our incoming message starts with hello, we can do this by using if statements, also known as branches. If the message is indeed “Hello” we want it to respond with something, get creative for the response 😊

```py
@client.event
async def on_message(message):
    if message.content.startswith('Hello'):
        client.send_message(message.channel, 'Hey, how are you?')
```

Ok, lets run it again just like before, and see if our bot responds!
 
![](https://i.imgur.com/igTTLOE.png)
 
But, we have one small issue now. If we type in “hello” it won’t respond, to fix this we want to change this line

```py
if message.content.startswith('Hello'):

if message.content.lower().startswith('hello'):
```

and with this little bit of extra code, we can now see that our bot responds to any kind of “hello”
 
![](https://i.imgur.com/2Rj0SaL.png)
