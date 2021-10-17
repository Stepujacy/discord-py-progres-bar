# discord-py-progres-bar

 
 Copy

```py
from PIL import Image, ImageFont, ImageDraw
from io import BytesIO
import random

@bot.command()
async def progres_bar(ctx):
    im = Image.open('bar01.jpg').convert('RGB')
    draw = ImageDraw.Draw(im)
    color=(255,0,0)
    x = random.randrange(0, 1000)
    y, diam = 8, 34
    draw.ellipse([x,y,x+diam,y+diam], fill=color)
    ImageDraw.floodfill(im, xy=(14,24), value=color, thresh=40)
    font = ImageFont.truetype("arial.ttf", 30)
    draw = ImageDraw.Draw(im)
    text = f'{x/10}%'
    color2 = (0,0,0)
    draw.text((460,10), text, color2, font=font)
    im.save('bar02.png')
    await ctx.send(file = discord.File("bar02.png"))
```
![alt text](https://cdn.discordapp.com/attachments/871410718224822302/873584604525781054/bar02.png)


