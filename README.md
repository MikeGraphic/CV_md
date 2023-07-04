# Summary

## 1. Name and Surname
Mihail Gavrilenko

## 2. Contacts
- Phone: +375(44)455-68-72
- Email: mikegraphics@mail.ru
- GitHub: https://github.com/MikeGraphic
- VK: https://vk.com/miki_qq

## 3. Brief information about yourself
My goal and priority is to continue to develop in the field of design and web development, providing customers with high-quality and innovative solutions. I have creative thinking, communication skills and the ability to translate ideas into unique design concepts.

 With my freelance and enterprise experience as a designer, I have developed project management, self-organization and customer interaction skills. My experience also includes website development and execution of design orders. I strive for professional growth, reflecting the client's uniqueness and achieving high results in the business environment.

## 4. Skills
- Programming languages: C#, JavaScript.
- Frameworks: Vue.js, React.js, Discord.js, Bootstrap.
- Version control systems: Git.
- Development tools: Visul Stidio, Visual Studio Code, Open Server, WebStorm, Sublime Text 3, Adobe Illustrator, Adobe Photoshop, Figma.

## 5. Code examples
```js
//JavaScript
const {
    Client,
    Collection,
    GatewayIntentBits
} = require('discord.js');
const fs = require('fs');

const client = new Client({
    intents: [GatewayIntentBits.Guilds]
});
const config = require('./data.json');
client.commands = new Collection();

fs.readdir('./commands', (err, files) => {
    if (err) console.log(err);

    let jsfile = files.filter(f => f.split('.').pop() === 'js');
    if (jsfile.length <= 0) return console.log('No commands found!');

    console.log(`Loaded ${jsfile.length} commands');
    jsfile.forEach((f, i) => {
        let props = require(`./commands/${f}`);
        client.commands.set(props.help.name, props);
    });
});

client.on('ready', () => {
    console.log(`Bot ${client.user.username} started`);
});

client.on('messageCreate', async message => {
    let prefix = config.prefix;
    if (!message.content.startsWith(prefix) || message.author.bot) return;
    let messageArray = message.content.split(' ');
    let command = messageArray[0];
    let args = messageArray.slice(1);

    let command_file = client.commands.get(command.slice(prefix.length));
    if (command_file) command_file.run(client, message, args, prefix);
});

client.login(config.token);
```

## 6. Work experience and training projects

### Project 1: Discord Bot Amy
- Link to [project repository on GitHub](https://github.com/MikeGraphic/DiscordBot )
- Skills used: JavaScript, Discord API: Discord.js,npm.
### Project 2: Logos of the specialty electronic marketing
- [Logo 1](/Logo2.jpg)
- [Logo 2](/Logo3.jpg)
- [Logo 3](/Logo4.jpg)
- Skills used: The basics of graphic design, the use of vector graphic tools, typography.

### Order 1: Development of the Start Music Studio logo 
- [Logo](/Logo(JPG).jpg )
- Skills used: The basics of graphic design, the use of vector graphic tools, typography.

## 7. Courses and trainings
- Completion of an educational program at the National Technical Park for the development of Web design

## 8. English
The level of English is B1. I speak English well enough to read documentation, communicate and learn new technologies.

## 9. Photo
![Photo](/S4jcSywGUeI.jpg )