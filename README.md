# Лилли

Бот, пересылающий посты из групп **[VK]** в **[Discord]**.

![](https://cdn.discordapp.com/attachments/580822197933965313/627232875070095360/scr.png)

Пересылка работает по принципу: ***не более одного самого популярного поста из текущей группы за определённый период***.

Тоесть, если Вам необходимо, чтобы на Вашем **[Discord]** сервере общение разбавлялось произвольными [постами][VK], например, **не более раза в 20 минут**, *не засоряя* канал всем доступным контентом - **этот бот Вам подходит**.

Бот выбирает текущую группу из доступного списка **по очереди**. 

Поддерживаются только эти виды постов:
- Простой текст
- Одно изображение с текстом или без
- Одна ссылка с текстом или без
- Одна фотография и одна ссылка с текстом или без

**Видео, гифки, аудио, несколько изображений в одном посте - не поддерживаются (ограничение [Discord] Embeds).**

### Данный бот не спроектирован для моментальной пересылки всего доступного контента.

# Запуск

Необходимо установить зависимости:
`pip install discord.py vk`

Далее необходимо отредактировать файл `config.py` и заполнить следующие значения:
- `vk_access_token` - [ключ доступа **VK**][VKtoken]
- `discord_token` - [токен **Discord**][Discordtoken]
- `vk_to_discord_timeout` - как часто осуществлять пересылку поста из **[VK]** в секундах

*По умолчанию: `300` сек., т.е. 5 минут*
- `vk_group_ids` - список групп **[VK]** из которых необходимо пересылать посты

*[Необходимо указывать их **ID**][GetVKID]*
- `vk_to_discord_channel_id` - **ID [Discord]** канала в который будут поступать посты из **[VK]**

После этого можно запускать:
`python gil.py`

Протестировано на  `Python 3.8`, `discord.py 2.0.0` и `vk 3.0`.

### Мгновенная пересылка из Discord в Discord

Бот также умеет моментально пересылать сообщения с нескольких **[Discord]** каналов в один.

Для этого заполните следующие значения в `config.py`:
- `discord_channel_ids` - список **ID** прослушиваемых **[Discord]** каналов

*Бот должен находиться на серверах этих каналов*
- `discord_to_discord_channel_id` - **ID [Discord]** канала в который будут моментально поступать сообщения из прослушиваемых **[Discord]** каналов

### Дополнительные настройки

- `game_name` - текст статуса бота в **[Discord]**
- `vk_bad_words` - текст поста **[VK]** будет обрезаться после строк указанных в этом значении (отдельно для каждой группы)
- `vk_embed_footer` - футер, который будет присоединяться к **каждому** пересланному посту
- `discord_bad_words` - эти строки будут полностью вырезаться из пересылаемых сообщений **из Discord в Discord** - используется для отключения пингов **here / everyone**
- `discord_urls` - используется для задания постоянной ссылки всем сообщениям пересылаемым с определенного **[Discord]** сервера
- `embed_color` - цвет эмбеддинга в **[Discord]**

[VK]: https://vk.com
[Discord]: https://discordapp.com/
[VKtoken]: https://vk.com/dev/access_token
[Discordtoken]: https://discordapp.com/developers/applications/
[GetVKID]: http://letmegooglethat.com/?q=%D0%BA%D0%B0%D0%BA+%D1%83%D0%B7%D0%BD%D0%B0%D1%82%D1%8C+id+%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D1%8B+%D0%B2%D0%BA
