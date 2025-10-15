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
```py

import inkcord
from inkcord import Client, BitIntents
import inkcord.utility as util
# note that in this version, all the import items are clumped together into inkcord, but it will be changed to this type of structure in later updates
intents = BitIntents.all()
bot = Client(token="TOKEN HERE",intents=intents)

@bot.