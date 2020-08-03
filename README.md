# Swiftcord
![Swiftcord](https://i.imgur.com/1Tq6KDb.png)

Simple & easy to use image manipulation module.

# Installing

```bash
npm i --save swiftcord
```

# Features
- Super fast image manipulation
- Welcomer abd leaver images
- Rank card
- and more...

# Functions
- batslap(image1, image2)
- beautiful(image)
- facepalm(image)
- gay(image)
- kiss(image1, image2)
- rip(image)
- spank(image1, image2)
- trash(image)
- blur(image, level = 5)
- greyscale(image)
- sepia(image)
- invert(image)
- delete(image)
- color(color_hex_or_html5_color_name)
- trigger(image)
- hitler(image)
- bed(image1, image2)
- wanted(image)
- circle(image)
- jail(image)
- dither(image)
- rank({ username, discrim, level, rank, neededXP, currentXP, avatarURL })

# Example

```js

const Swiftcord = require("swiftcord");
const canva = new Swiftcord.Canvas();
const fs = require("fs");

function create() {
    fs.readFile("./image.png", async (err, data) => {
        let img = await canva.trigger(data);
        return fs.writeFile("./triggered.gif", img, (err) => {
            if (err) console.error(err);
        });
    });
}

create();

```

# Discord.js Example

```js
const Discord = require("discord.js");
const client = new Discord.Client();
const Swiftcord = require("swiftcord");
const canva = new Swiftcord.Canvas();

client.on("ready", () => {
    console.log("I'm online!");
});

client.on("message", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!trigger") {
        let avatar = message.author.displayAvatarURL({ dynamic: false, format: 'png' });
        let image = await canva.trigger(avatar);
        let attachment = new Discord.MessageAttachment(image, "triggered.gif");
        return message.channel.send(attachment);
    }
    if (message.content === "!delete") {
        let avatar = message.author.displayAvatarURL({ dynamic: false, format: 'png' });
        let image = await canva.delete(avatar);
        let attachment = new Discord.MessageAttachment(image, "deleted.png");
        return message.channel.send(attachment);
    }
});

client.login("Your_Bot_Token_here");

```
# Example Welcome

```js
const Discord = require("discord.js");
const client = new Discord.Client();
const Swiftcord = require("swiftcord");
const canva = new Swiftcord.Canvas();

let image = await canva.Welcome()
    .setUsername("Atzu🥀")
    .setDiscriminator("0001")
    .setMemberCount("18")
    .setGuildName("Pruebas Bots")
    .setAvatar("https://www.site.com/avatar.jpg")
    .setColor("border", "#7289da")
    .setColor("username-box", "#7289da")
    .setColor("discriminator-box", "#7289da")
    .setColor("message-box", "#7289da")
    .setColor("title", "#7289da")
    .setColor("avatar", "#7289da")
    .setBackground("https://i.atzu.xyz/atzu-cabc.png")
    .toAttachment();
      
let attachment = new Discord.MessageAttachment(image.toBuffer(), "welcome.png");
return message.channel.send(attachment);
```
![image](https://i.imgur.com/HhV6X8c.png)

# Preview
![image](https://i.imgur.com/P68XUqq.png)

# Join Our Discord Server
**[discord.gg/q99CQEP](https://discord.gg/q99CQEP)**
