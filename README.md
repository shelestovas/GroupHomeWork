# Групповое задание для JS1 группы, обязательно к прочтению

### Установка

Сначала клонируем репозиторий, а затем обновляем пакеты:

```
$ npm update
```

После этой команды все зависимости которые указаны в `package.json` будут загружен на компьютер в папку node_modules.
Папку `node_modules` заливать на репозиторий не нужно, в `.gitignore` это указано.

### Структура

| Папка | Описание |
| ------ | ------ |
| dist | Здесь будут все файлы собранные gulp'ом |
| src | Файлы и папки из которых будет компилироваться шаблон в папку `dist` |
| bootstrap_theme | Скаченный  шаблон landingpage, эти файлы не редактируем, работаем в папке src |
| node_modules | Папка с установленными модулями, в репозитории не должнобыть |

### Формат работы

Далее я опишу как я представляю себе командную работу с проектом в git'e, т.к. для меня это впервые то возможно оно будет не правильным. А может так как надо, хз, посмотрим)))

Ниже будут таблицы с колонками "Ответственный", в эту колонку желающий пишет свою Имя и Фамилию и работает над этой частью.

#### 1. Создание gulp файла

Лично я создавал gulp файл по вот этой статье: [https://habrahabr.ru/post/250569/](https://habrahabr.ru/post/250569/).
Мне кажется удобно, текущая структура взята с этой статьи.
Все предлагаемые пакеты уже должны быть установленны после клонирования репозитория и выполнения команды `$ npm update`.
Думаю можно делать все по статье, нам главное научится правильно работать толпой людей с одним файлом в git'e.
Нужны люди которые сделают:

| Действие | Ответственный |
| ------ | ------ |
| Создаст сам файл gulp.js, пропишет все зависимости, пути, конфиги и потом скажет остальным что можно работать с файлом дальше. А потом как остальные все свое сделают, дособрать файл до полной готовности. | - |
| - Создать код сборки pug файлов в html и image файлов | - |
| - Создать код сбоки sass и js файлов | - |
| - Создать код сбоки font файлов(fontawesome и glyphicons из bootstrap) | - |

#### 2. Переработка шаблона в *.pug и *.sass формат

Скаченный шаблон распологается в папке `bootstrap_template` переработанные исходники должны распологаться в папке src.
Шаблон в сети [https://blackrockdigital.github.io/startbootstrap-creative/](https://blackrockdigital.github.io/startbootstrap-creative/)

В шаблоне используется несколько плагинов которые нужно будет установить командой
```
$ npm install jquery bootstrap font-awesome magnific-popup scrollreveal --save
```
файл `package.json` обновится и его тоже нужно будет обновить на git, чтобы другие смогли сделать себе pull и потом командой `$ npm update` обновить свои плагины до актуального состояния.

Думаю это должен сделать ответственный за создание файла `index.pug`.

##### 2.1 Создание *.pug файлов
Изображения использующиеся в верстке соответственно кидать в src/img.
Нужны люди которые сделают:

| Действие | Ответственный |
| ------ | ------ |
| Создаст файл index.pug в корне папки src с началом и концом страницы, подлюченными стилями(main.css) и скриптам(main.js), БЕЗ контента. Скажет остальным что можно делать контент. Как остальные доделают свою часть, дособрать файл через include *.pug | - |
| - Переработает в *.pug меню и первый блок | - |
| - Переработает в *.pug второй и третий(с иконками) блоки | - |
| - Переработает в *.pug блок с фотками(6 шт) | - |
| - Переработает в *.pug последние 2 блока | - |

##### 2.1 Создание *.sass файлов
Изображения использующиеся в верстке соответственно кидать в src/img.
Аналогично как и с *.pug
Нужны люди которые сделают:

| Действие | Ответственный |
| ------ | ------ |
| Создаст файл main.sass в папке src/style . Скажет остальным что можно делать стили блоков. Как остальные доделают свою часть, дособрать файл main.sass через @import *.sass. И еще через импорт подключит css файлы используемых в шаблоне плагинов | - |
| - Переработает в *.sass стили меню и первый блок и сохранит файл в src/style/partials | - |
| - Переработает в *.sass второй и третий(с иконками) блоки и сохранит файл в src/style/partials | - |
| - Переработает в *.sass блок с фотками(6 шт) и сохранит файл в src/style/partials | - |
| - Переработает в *.sass последние 2 блока и сохранит файл в src/style/partials | - |

##### 2.2 Создание *.js файлов
Аналогично как и с *.sass
Нужны люди которые сделают:

| Действие | Ответственный |
| ------ | ------ |
| Создаст файл main.js в папке src/js. Добавит в этот файл, но лучше в файл src/js/partials/*.js js код шаблона, его там немного. И еще через gulp-rigger(см. статью хабра про gulp) подключит js файлы используемых в шаблоне плагинов | - |

##### 2.3 Файлы со шрифтами
Элементарное задание.

| Действие | Ответственный |
| ------ | ------ |
| Скопировать шрифты fontawesome и glyphicons из bootstrap в папку src/fonts, потом они через gulp соберутся | - |

#### Вроде все! =)