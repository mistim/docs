
<!-- > **Note:** If you do not want to install yet, you can follow along in this guide with the [online editor](http://elm-lang.org/try) and the [online REPL](http://elmrepl.cuberoot.in/).
-->

 > **Примечание:** Если вы еще не хотите устанавливать, вы можете следовать этому руководству с помощью [онлайн-редактора](http://elm-lang.org/try) и [онлайн REPL](http://elmrepl.cuberoot.in/

<!-- 
# Install
 -->

# Установка

<!-- 
  * Mac &mdash; [installer][mac]
  * Windows &mdash; [installer][win]
  * Anywhere &mdash; [npm installer][npm] or [build from source][build]
 -->

* Mac &mdash; [Установщик][mac]
* Windows &mdash; [Установщик][win]
* Anywhere &mdash; [npm installer][npm] или [build from source][build]

[mac]: http://install.elm-lang.org/Elm-Platform-0.18.pkg
[win]: http://install.elm-lang.org/Elm-Platform-0.18.exe
[npm]: https://www.npmjs.com/package/elm
[build]: https://github.com/elm-lang/elm-platform

<!-- 
After installing through any of those routes, you will have the following command line tools:

- [`elm-repl`](#elm-repl) &mdash; play with Elm expressions
- [`elm-reactor`](#elm-reactor) &mdash; get a project going quickly
- [`elm-make`](#elm-make) &mdash; compile Elm code directly
- [`elm-package`](#elm-package) &mdash; download packages
 -->

После установки через любой из этих маршрутов у вас будут следующие средства командной строки:

- [`elm-repl`](#elm-repl) &mdash; играть с выражениями Elm
- [`elm-reactor`](#elm-reactor) &mdash; быстро получить проект
- [`elm-make`](#elm-make) &mdash; скомпилировать код Elm
- [`elm-package`](#elm-package) &mdash; скачать пакеты

<!-- 
We will go over how they all work in more detail right after we get your editor set up!
 -->

Мы рассмотрим, как все они работает более подробно сразу после создания вашего редактора!

<!-- 
> **Troubleshooting:** The fastest way to learn *anything* is to talk with other people in the Elm community. We are friendly and happy to help! So if you get stuck during installation or encounter something weird, visit [the Elm Slack](http://elmlang.herokuapp.com/) and ask about it. In fact, if you run into something confusing at any point while learning or using Elm, come ask us about it. You can save yourself hours. Just do it!
 -->

> **Устранение неполадок:** Самый быстрый способ узнать *что-либо* - поговорить с другими людьми сообщества Elm. Мы дружелюбны и рады помочь! Поэтому, если вы застряли во время установки или столкнулись с чем-то странным, посетите [Elm Slack](http://elmlang.herokuapp.com/) и спросите об этом. На самом деле, если вы сталкиваетесь с чем-то запутанным в любой момент во время обучения или использования Elm, спросите нас об этом. Вы можете сэкономить часы. Просто сделате это!

<!-- 
## Configure Your Editor
 -->

## Настройте свой редактор

<!-- 
Using Elm is way nicer when you have a code editor to help you out. There are Elm plugins for at least the following editors:
 -->

Использование Elm лучше, когда у вас есть редактор кода, который поможет вам. Есть плагины для Elm, по крайней мере, для следующих редакторов:

  * [Atom](https://atom.io/packages/language-elm)
  * [Brackets](https://github.com/lepinay/elm-brackets)
  * [Emacs](https://github.com/jcollard/elm-mode)
  * [IntelliJ](https://github.com/durkiewicz/elm-plugin)
  * [Light Table](https://github.com/rundis/elm-light)
  * [Sublime Text](https://packagecontrol.io/packages/Elm%20Language%20Support)
  * [Vim](https://github.com/ElmCast/elm-vim)
  * [VS Code](https://github.com/sbrink/vscode-elm)

<!-- 
If you do not have an editor at all, [Sublime Text](https://www.sublimetext.com/) is a great one to get started with!
 -->

Если у вас нет редактора вообще, [Sublime Text](https://www.sublimetext.com/) - отличный способ начать работу с ним!

<!-- 
You may also want to try out [elm-format][] which makes your code pretty!
 -->

Вы также можете попробовать [elm-format][], который делает ваш код симпатичным!

[elm-format]: https://github.com/avh4/elm-format

<!-- 
## The Command Line Tools
 -->

## Инструменты командной строки

<!-- 
So we installed Elm, and it gave us `elm-repl`, `elm-reactor`, `elm-make`, and `elm-package`. But what do they all do exactly?
 -->

Поэтому мы установили Elm, и это дало нам `elm-repl`, `elm-reactor`, `elm-make` и `elm-package`. Но что они все делают точно?

### elm-repl

<!-- 
[`elm-repl`](https://github.com/elm-lang/elm-repl) lets you play with simple Elm expressions.
 -->

[`elm-repl`](https://github.com/elm-lang/elm-repl) позволяет вам играть с помощью простых выражений Elm.

```bash
$ elm-repl
---- elm-repl 0.18.0 -----------------------------------------------------------
 :help for help, :exit to exit, more at <https://github.com/elm-lang/elm-repl>
--------------------------------------------------------------------------------
> 1 / 2
0.5 : Float
> List.length [1,2,3,4]
4 : Int
> String.reverse "stressed"
"desserts" : String
> :exit
$
```

<!-- 
We will be using `elm-repl` in the upcoming &ldquo;Core Language&rdquo; section, and you can read more about how it works [here](https://github.com/elm-lang/elm-repl/blob/master/README.md).
 -->

Мы будем использовать `elm-repl` в предстоящем &ldquo;Core Language&rdquo; раздел, и вы можете узнать больше о том, как это работает [здесь](https://github.com/elm-lang/elm-repl/blob/master/README.md).

<!-- 
> **Note:** `elm-repl` works by compiling code to JavaScript, so make sure you have [Node.js](http://nodejs.org/) installed. We use that to evaluate code.
 -->

> **Примечание:** `elm-repl` работает, компилируя код на JavaScript, поэтому убедитесь, что у вас установлен [Node.js](http://nodejs.org/). Мы используем это для оценки кода.

### elm-reactor

<!-- 
[`elm-reactor`](https://github.com/elm-lang/elm-reactor) helps you build Elm projects without messing with the command-line too much. You just run it at the root of your project, like this:
 -->

[`elm-reactor`](https://github.com/elm-lang/elm-reactor) помогает вам создавать проекты Elm, не слишком запускаясь с командной строкой. Вы просто запускаете его в корне своего проекта, например:

```bash
git clone https://github.com/evancz/elm-architecture-tutorial.git
cd elm-architecture-tutorial
elm-reactor
```

<!-- 
This starts a server at [`http://localhost:8000`](http://localhost:8000). You can navigate to any Elm file and see what it looks like. Try to check out `examples/01-button.elm`.
 -->

Это запустит сервер в [`http://localhost:8000`](http://localhost:8000). Вы можете перейти к любому вложенному файлу и посмотреть, как он выглядит. Попробуйте проверить `examples/01-button.elm`.

<!-- 
**Notable flags:**

- `--port` lets you pick something besides port 8000. So you can say
  `elm-reactor --port=8123` to get things to run at `http://localhost:8123`.
- `--address` lets you replace `localhost` with some other address. For
  example, you may want to use `elm-reactor --address=0.0.0.0` if you want to
  try out an Elm program on a mobile device through your local network.
 -->

**Значимые флаги:**

- `--port` позволяет вам выбрать что-то помимо порта 8000. Таким образом, вы можете сказать `elm-reactor --port=8123`, чтобы заставить вещи работать на` http://localhost:8123`.
- `--address` позволяет вам заменить localhost на другой адрес. Для например, вы можете использовать `elm-reactor -address=0.0.0.0`, если хотите попробуйте программу Elm на мобильном устройстве через вашу локальную сеть.

### elm-make

<!-- 
[`elm-make`](https://github.com/elm-lang/elm-make) builds Elm projects. It can compile Elm code to HTML or JavaScript. It is the most general way to compile Elm code, so if your project becomes too advanced for `elm-reactor`, you will want to start using `elm-make` directly.
 -->

[`elm-make`](https://github.com/elm-lang/elm-make) создает проекты Elm. Он может скомпилировать код Elm в HTML или JavaScript. Это самый общий способ скомпоновать код Elm, поэтому, если ваш проект станет слишком продвинутым для `elm-reactor`, вы захотите начать использовать` elm-make` напрямую.

<!-- 
Say you want to compile `Main.elm` to an HTML file named `main.html`. You would run this command:
 -->

Предположим, вы хотите скомпилировать `Main.elm` в файл HTML с именем `main.html`. Вы должны выполнить эту команду:

```bash
elm-make Main.elm --output=main.html
```

<!-- 
**Notable flags:**

- `--warn` prints warnings to improve code quality
 -->

**Значимые флаги:**

- `--warn` печатает предупреждения для улучшения качества кода


### elm-package

<!-- 
[`elm-package`](https://github.com/elm-lang/elm-package) downloads and publishes packages from our [package catalog](http://package.elm-lang.org/). As community members solve problems [in a nice way](http://package.elm-lang.org/help/design-guidelines), they share their code in the package catalog for anyone to use!
 -->

[`elm-package`](https://github.com/elm-lang/elm-package) загружает и публикует пакеты из нашего [каталога пакетов](http://package.elm-lang.org/). Поскольку члены сообщества решают проблемы [красивым способом](http://package.elm-lang.org/help/design-guidelines), они делятся своим кодом в каталоге пакетов для тех, кто их использует!

<!-- 
Say you want to use [`elm-lang/http`][http] and [`NoRedInk/elm-decode-pipeline`][pipe] to make HTTP requests to a server and turn the resulting JSON into Elm values. You would say:
 -->

Предположим, вы хотите использовать [`elm-lang/http`] [http] и [`NoRedInk/elm-decode-pipe`] [pipe], чтобы сделать HTTP-запросы на сервер и превратить полученные JSON в значения Elm. Вы бы сказали:

[http]: http://package.elm-lang.org/packages/elm-lang/http/latest
[pipe]: http://package.elm-lang.org/packages/NoRedInk/elm-decode-pipeline/latest

```bash
elm-package install elm-lang/http
elm-package install NoRedInk/elm-decode-pipeline
```

<!-- 
This will add the dependencies to your `elm-package.json` file that describes your project. (Or create it if you do not have one yet!) More information about all this [here](https://github.com/elm-lang/elm-package)!
 -->

Это добавит зависимости к вашему файлу `elm-package.json`, который описывает ваш проект. (Или создать его, если у вас его еще нет!) Дополнительная информация обо всем этом [здесь] (https://github.com/elm-lang/elm-package)!

<!-- 
**Notable commands:**

- `install`: install the dependencies in `elm-package.json`
- `publish`: publish your library to the Elm Package Catalog
- `bump`: bump version numbers based on API changes
- `diff`: get the difference between two APIs
 -->

** Известные команды: **

- `install`: установить зависимости в `elm-package.json`
- `publish`: опубликовать вашу библиотеку в каталоге пакета Elm
- `bump`: номера версий bump на основе изменений API
- `diff`: получить разницу между двумя API