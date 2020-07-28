# vtb-bco-plugin

### Расширение BCO сайта "ВТБ Бизнес онлайн" https://bo.vtb24.ru для браузера Google Chrome под Mac OS 10.14+

> По заявлению техподдержки ВТБ расширение не работает в браузере Google Chrome под Mac OS 10.14+. 

## Предисловие

Мне надоело прыгать из Chrome в Firefox (там плагин работает, но под Catalina не без бубна) и пришлось заняться починкой.

Двоичный код плагина никак не изменялся. Был изменен только файл `mainfest.json`

Работает в Google Chrome версии 84.0.4147.89

## Устанавка расширения в Chrome под Mac OS 

1. Установить расширение с сайта ВТБ [https://bo.vtb24.ru/login](https://bo.vtb24.ru/login)
2. Скачать модифицированный код расширения на свой компьютер.
3. Открыть страницу `chrome://extensions/`
4. Переключиться в `Режим разработчика`
5. Кликнуть кнопку `Загрузить распакованное расширение`
6. Вырать из каталога куда вы сохранили расширение каталог `src`
7. Кликнуть по кнопке `Выбрать`
8. Открыть в текстовом редакторе файл `~/Library/Application Support/Google/Chrome/NativeMessagingHosts/ru.signalcom.bco.firewyrmhost.json`
9. Найти в этом файле строку похожую на это `"allowed_origins": ["chrome-extension://nhkicjknlfaglcjpgmafhkmlempcbifb/"]`
10. Заменить набор непонятных букв на другие непонятные буквы. `"allowed_origins": ["chrome-extension://вот_сюда_вставить_новые_непонятные_буквы/"]`

## Где найти непонятные буквы для замены?

Непонятные буквы - это идентификатор расширения. Найти его можно на странице `Расширения` в Google Chrome.

1. В адресную строку браузера Chrome ввсти адрес `chrome://extensions/`
2. Переключить страницу в `Режим разработчика`
3. Найти на странице `Расширения` - расширение `Bco Plugin Adapter`
4. Кликнуть по кнопке `Подробнее`
5. Найти слово `Идентификатор` - под ним новый идетификатор расширения
6. Скопировать идентификатор и вставить в файл `~/Library/Application Support/Google/Chrome/NativeMessagingHosts/ru.signalcom.bco.firewyrmhost.json` как описано выше.

#### Файл `ru.signalcom.bco.firewyrmhost.json` содержит текст в формате JSON:

```JSON
{
   "name": "ru.signalcom.bco.firewyrmhost",
   "description": "BCO System Cryptographic Plugin Adapter",
   "path": "/Users/den/Library/Internet Plug-Ins/Bco.plugin/Contents/Resources/FireWyrmNativeMessageHost",
   "type": "stdio",
   "allowed_origins": ["chrome-extension://nhkicjknlfaglcjpgmafhkmlempcbifb/"]
}
```

## Права и ответственность

Пагин поставляется как есть. Все его содержимое взято из оригинального файла `bco.pkg`, скачанного с сайта ВТБ.

Все права на плагин принадлежат разработчику (вероятно банку ВТБ).

Я никакой ответственности за использование плагина не несу. 

Используйте его на свой страх и риск. 
