# Резюме

## 1. Имя и Фамилия
Михаил Гавриленко

## 2. Контакты
- Телефон: +375(44)455-68-72
- Email: mikegraphics@mail.ru
- GitHub: https://github.com/MikeGraphic
- VK: https://vk.com/miki_qq

## 3. Краткая информация о себе
Моя цель и приоритет - продолжать развиваться в области дизайна и веб-разработки, предоставляя клиентам качественные и инновационные решения. Я обладаю творческим мышлением, коммуникативными навыками и способностью воплощать идеи в уникальные дизайнерские концепции.

 С опытом работы на фрилансе и на предприятии дизайнером, я развил навыки управления проектами, самоорганизации и взаимодействия с клиентами. Мой опыт также включает разработку веб-сайтов и выполнение заказов по дизайну. Я стремлюсь к профессиональному росту, отражая клиентскую уникальность и достигая высоких результатов в деловой среде.

## 4. Навыки
- Языки программирования: С#, JavaScript.
- Фреймворки: Vue.js, React.js, Discord.js, Bootstrap.
- Системы контроля версий: Git.
- Инструменты разработки: Visul Stidio, Visual Studio Code, Open Server, WebStorm, Sublime Text 3, Adobe Illustrator, Adobe Photoshop, Figma.

## 5. Примеры кода
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
    if (jsfile.length <= 0) return console.log('Команды не найдены!');

    console.log(`Загружено ${jsfile.length} команд`);
    jsfile.forEach((f, i) => {
        let props = require(`./commands/${f}`);
        client.commands.set(props.help.name, props);
    });
});

client.on('ready', () => {
    console.log(`Бот ${client.user.username} запустился`);
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

## 6. Опыт работы и учебные проекты

### Проект 1: Discord Bot Amy
- Ссылка на [репозиторий проекта на GitHub](https://github.com/MikeGraphic/DiscordBot)
- Использованные навыки: JavaScript, Discord API: Discord.js,npm.

### Заказ 1: Разработка логотипа Музыкальной студии Start 
- Ссылка на [репозиторий проекта на GitHub](https://github.com/MikeGraphic/StartMusicalStudio)
- Использованные навыки: Основы граффического дизайна, Использование векторных графических инструментов, типографика.

## 7. Курсы и тренинги
- Прохождение образовательной программы в национальном техническом парке по напровлению Web-дизайн

## 8. Английский язык
Уровень английского языка - B1. Я владею английским достаточно хорошо для чтения документации, общения и изучения новых технологий.

## 9. Фото
![Фото](ссылка_на_фото_или_аватарку.jpg)
