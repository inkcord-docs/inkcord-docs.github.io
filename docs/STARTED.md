# Getting Started
You will need prerequisites to run a file with this library, but they are very self-explanatory:
- Python version 3.8 or later
(see, I told you they were self explanatory)
To install, (if you haven't already) it's very simple. Just run
```
pip install inkcord
```
with the version you want specified using ==, in your virtual environment/python environment.

## First Bot
To make your first bot with commands, you will need to create an application in the [Discord Dev Portal](https://discord.com/developers/applications).
After you have done that, click on your application, and navigate to the "Bot" page as listed in the menu to the left of your screen.
Click the "Reset Token" button to recieve your token that you will need for your bot to run. (Note that this may require authentication)
![](images/png%20for%20tokens.png)

### Python Code
* Note: To understand this code/debug it if there's a bug (if there is, make a PR on the library repo), you will require a somewhat intermediate language of Python.

**Full Code**
```python

import inkcord
from inkcord import Client
import inkcord.utility as util
# note that in this version, all the import items are clumped together into inkcord.
# will be updated in next update
intents = util.BitIntents.all() # in actual, non example projects, this is VERY MUCH not recommended.
bot = Client(token="TOKEN HERE",intents=intents)

@bot.command(name="example",description="I'm an example command! Run me!!!!")
async def exampl(inter: inkcord.SlashInteraction):
    # note that the function HAS to be asynchronous
    inter.response("Hey, I'm an interaction command!")

@bot.prereq()
async def sync_all():
    await bot.sync()

bot.run()
```
You will need the `sync()` function to make sure your commands are up to date and they show in the discord client.
When you use this command, you will see the bot respond with "Hey, I'm an interaction command!".
For more advanced projects, you can use this website for reference.
