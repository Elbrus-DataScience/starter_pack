# Welcome

Привет, Эльбрусовец!

Поздравляю, ты прошел непростой путь и уже в понедельник начнется твой путь самурая в Elbrus Bootcamp.
Давай разберемся с тем, что тебе необходимо сделать, чтобы быть во всеоружии к старту обучения:

# Настройка рабочего окружения
<details>
<summary>1. Установка UNIX системы</summary>
<br>
    
Если у тебя MacOS - пропусти этот шаг, Ubuntu устанавливать не нужно  

Для наиболее производительной и комфортной работы вам понадобится [Unix-подобная операционная система](https://ru.wikipedia.org/wiki/Unix-подобная_операционная_система).   
Если вы решаете остаться на Windows - тогда отвественность за решение проблем работы на ней вы принимаете на себя, на свой страх и риск. Надежнее вместо Windows использовать Linux, например Ubuntu.  
  
Инструкций по установке огромное множество. Можно воспользоваться [официальной инструкцией](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview) или вот [этой](https://losst.pro/ustanovka-ubuntu-22-04) на русском.   
Основная рекомендация по установке заключаются в выборе для установки последней Long-term support (LTS) [версии](https://releases.ubuntu.com/jammy/), так вы сможете получить наиболее стабильную систему, проблем при установке библиотек машинного обучения в будущем с такой версией должно быть меньше всего.  

#### Дополнительные материалы
- 📽 [Основы Ubuntu](https://youtu.be/tQLpAefAKuA)
- 🇸 [Введение в Linux](https://stepik.org/course/73/promo)
</details>


<details>
<summary>2. GitHub </summary>
  <br>
  
  Для начала посмотри [лекцию по github](https://youtu.be/4TRClQ7rttw)  
  
  <details>
  <summary>2.1 Что такое GitHub?</summary>
  <br>
    
  GitHub - это [cистема управления версиями](https://ru.wikipedia.org/wiki/Система_управления_версиями) с социальной составляющей. В соцсети вы выкладываете фотографии, а тут исходный код. Это ещё и самая большая площадка для opensource     проектов. Веб-сервис основан на [системе](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) контроля версий [Git](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F). Ну и конечно, вы можете сделать свою гитхаб страницу своим [*резюме*](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme).
  </details>

 <details>
 <summary>2.2 Настройка доступа по SSH</summary>
 <br>
   
  Для начала настроим доступ к репозиториям аккаунта. 
  
  ### Пример для Linux(Ubuntu)
  
  - откройте терминал (`Ctrl + Alt + T`) на своём компьютере и выполните ряд команд
     * `обновление списков пакетов для обновлений`
     * `установка пакета ssh`
      ``` 
      sudo apt update    
      sudo apt-get install ssh    
      ```
   
  **`на MacOS начинайте отсюда`**
  - далее мы запустим команды, для генерации собственных SSH-ключей (ed25519 - это [крипто-схема](https://ru.wikipedia.org/wiki/EdDSA))
      ```
      ssh-keygen -t ed25519 -C "подставь сюда свою почту, на которую регистрировался github и кавычки оставь"
      ```
     - нажми на Enter три раза (так проще, заполнять ответы/фразы не обязательно)
  
  
  
  Теперь в корневой папке твоего компьютера есть [*скрытая*](https://nextontext.ru/linux-i-os-x/646-skrytye-fajly-i-papki-v-ubuntu) папка `.ssh` (на mac `command+shift+.`), внутри лежат два файла `id_ed25519` и `id_ed25519.pub`. Первый - твой приватный ключ устройства, второй - публичный, его мы и будем использовать в качестве ключа на странице добавления публичных ключей в аккаунт [GitHub](https://github.com/settings/keys).
  
  - можно запустить [команду чтения](https://losst.ru/komanda-cat-linux) содержимого файла `cat .ssh/id_ed25519.pub`, 
  - выделить и скопировать из терминала, через сочетание клавиш `ctrl+shift+c`, содержимое публичного ключа (на mac просто `command+c`)
  - копируем всю строку от включительно `ssh-ed25519 ...` и до `... ваша@почта.com` включительно 
  - пора скопировать ключ на [GitHub](https://github.com/settings/ssh/new)
  - название `Title` можно задать любое, обычно такое, чтобы вам было понятно, о ключе с какого компьютера идёт речь
  
  </details>

  <details>
  <summary>2.3 Проверка настройки SSH или твой первый Fork</summary>
  <br>
  
  Когда ваша система уже настроена, получен и подключен SSH-ключ, вам ничего не мешает создать копию этого репозитория у себя в аккаунте. Нужно лишь нажать на кнопку `Fork` сверху справа на главной странице репозитория - `https://github.com/Elbrus-DataScience/starter_pack`
  
  Теперь можно перейти на свою страницу c репозиториями `https://github.com/USER?tab=repositories`, *здесь и далее* `USER` – ваш ник в GitHub. Второй вариант - вы кликаете на фото профиля в правом верхнем углу и переходим во вкладку `Your profile` или `Your repositories` для доступа к странице аккаунта и репозиториев соответственно.
  
  - переходим на страницу вашего форка (в поле ввода браузера должно быть `https://github.com/USER/starter_pack`)  
  - здесь нажимаем на *зелёную* кнопку <span style="color: green;">**Code**</span>  
  - выбираем вкладку <span style="text-decoration:underline">**SSH**</span>  
  - *копируем* ссылку на репозиторий (она должна быть такого вида: `git@github.com:USER/starter_pack.git`)  
  
  </details>

  <details>
  <summary>2.4 Дополнительные материалы</summary>
  <br>
  
  📑 Инструкция по генерации [ключа SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
  📑 Статья про fork на [GitHub](https://docs.github.com/en/get-started/quickstart/fork-a-repo)  
    
  </details>
</details>

<details>
<summary>3. Git</summary>
  <br>
  
  <details>
  <summary>Что такое Git?</summary>
  <br>
    
  Это [система контроля версий](https://ru.wikipedia.org/wiki/Git). 
  Вам она понадобится с первого дня работы. Работа с git-командами через терминал - это тот навык, который вам будет полезен. Но сначала будет достаточно уметь применять ряд простых команд и сценариев работы. 

  </details>

  <details>
  <summary>Установка  Git</summary>
  <br>
    
  При чистой установке Ubuntu 20.04 `git` по умолчанию не поставляется, как и для macOS. Можно проверить это в терминале (сочетание клавиш для linux `Ctrl + Alt + T`, на macOS - ищите `Terminal` (но рекомендую [установить](https://iterm2.com) `iTerm2` и использовать его) через Spotlight): напишите в новом окне `git`. Если терминал вам говорит, что такого пакета нет - идём его устанавливать.
[Следуйте инструкции для вашей ОС](https://git-scm.com/downloads)

  </details>


  
</details>

<details>
<summary>3. Conda</summary>
  
</details>


<details>
<summary>Ubuntu</summary>

### Установка VS Code
<details>
<summary>Через пакет</summary>
<br/>

- Переходим на сайт code.visualstudio.com, секция Download. Нажимаем и скачиваем себе на ПК.
- Устанавливаем
</details>

<details>
<summary>Через терминал</summary>

1. Заходим на оф.сайт https://code.visualstudio.com/docs/setup/setup-overview и выбираем Linux. По инструкции вводим следующие команды в терминал для Убунту

`sudo apt-get install wget gpg`\
`wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg`\
`sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg`\
`sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'`\
`rm -f packages.microsoft.gpg`\
`sudo apt install apt-transport-https`\
`sudo apt update`\
`sudo apt install code`
</details>

### Установка Git

- Ввести в терминал
`sudo apt update`\
Возможно, вас попросят ввести пароль. Введите пароль. <strong>Внимание:</strong> его не будет видно в терминале, это нормально.

`sudo apt upgrade`\
`sudo apt install git`

- Можно проверить, что у вас установился `git`, введя в терминале `git`. Должен открыться список команд.

### Настройка Git

1. В терминале необходимо ввести две команды
`git config --global user.name "Ваш никнейм на github"`
`git config --global user.email ВашEmailНаGithub@example.com`
2. Проверяем коммандой `git config --list`

### Генерация ключа  SSH

1. Открываем терминал
2. Вводим команду `ssh-keygen -t ed25519 -C "ваш_email@example.com"`
3. Приложение запросит место сохранения, предлагая по умолчанию, нажимаем `Enter`
4. Далее вам будет предложено ввести кодовую фразу. Нажмите клавишу `Enter`, чтобы пропустить
5. Подтверждение кодовой фразы также пропускаем
6. После генерации идем по пути из 3го пункта и открываем файл `id_ed25519.pub` любым текстовым редактором и копируем содержимое.
7. Идем в настройки аккаунта на GitHub

<div align="center">
    <img src="./assets/Рисунок15.png" width="200">
</div>

8. Нажимаем кнопку New SSH Key и в открывшемся окне вставляем содержимое из файла `id_ed25519.pub` и вводим название ключа

<div align="center">
    <img src="./assets/Рисунок16.png">
</div>

### Итог

На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub
</details>

<details>
<summary>MacOS</summary>

### Установка VS Code

1. Заходим на оф.сайт https://code.visualstudio.com/docs/setup/setup-overview и выбираем macOS. По инструкции открываем первую ссылку и скачиваем пакет в виде архива.
2. Нам необходимо распаковать архив и перетащить `Visual Studio Code.app` в папку `Applications`.
3. Добавим Visual Studio Code в `Dock`, выбрав в `Options` `«Keep in Dock»`

### Установка Git

- Если у вас нет пакетного менеджера Brew, необходимо сначала установить его. Переходит на оф. сайт и https://brew.sh/ и копируем команду оттуда
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`. Brew попросит ввести еще 2 команды: `echo 'eval $(/opt/homebrew/bin/brew shellenv)'  >> /Users/ИМЯ ТВОЕГО ПОЛЬЗОВАТЕЛЯ НА МАКЕ/.zprofile`. Следующим вводим команду`eval $(/opt/homebrew/bin/brew shellenv)`. Готово! 
- Затем вводим в терминал `brew install git`
- Можно проверить, что у вас установился `git`, введя в терминале `git`. Должен открыться список команд.


### Настройка Git

1. В терминале необходимо ввести две команды
`git config --global user.name "Ваш никнейм на github"`
`git config --global user.email ВашEmailНаGithub@example.com`
2. Проверяем коммандой `git config --list`

### Генерация ключа  SSH

1. Открываем терминал
2. Вводим команду `ssh-keygen -t ed25519 -C "ваш_email@example.com"`
3. Приложение запросит место сохранения, предлагая по умолчанию, нажимаем `Enter`
4. Далее вам будет предложено ввести кодовую фразу. Нажмите клавишу `Enter`, чтобы пропустить
5. Подтверждение кодовой фразы также пропускаем
6. После генерации идем по пути из 3го пункта и открываем его по команде `cat ~/.ssh/id_ed25519.pub` и копируем всё содержимое.
7. Идем в настройки аккаунта на GitHub

<div align="center">
    <img src="./assets/Рисунок15.png" width="200">
</div>

8. Нажимаем кнопку New SSH Key и в открывшемся окне вставляем содержимое из файла `id_ed25519.pub` и вводим название ключа

<div align="center">
    <img src="./assets/Рисунок16.png">
</div>

### Итог

На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub
</details>

# Оптимизация работы в VSCode

<details>
<summary>Автосохранение</summary>
Настройте в VSCode автоматическое сохранение файла при редактировании.

<div align="center">
    <img src="./assets/auto-save.jpg">
</div>

</details>

<details>
<summary>Расширения</summary>

### Juputer
> Расширение позволяет автоматически перезагружать страницу после внесения изменений в js, css, html-код. Это упрощает отладку отдельных HTML-страниц со скриптами.

После установки в правом нижнем углу появится кнопка `Go Live`. Достаточно открыть в VSCode html документ, нажать на кнопку `Go Live` и спустя несколько секунд html автоматически откроется в вашем браузере по умолчанию.

### Rainbow CSV
> Расширение позволяет запускать js код внутри VSCode.

После установки в правом верхнем углу появится кнопка в виде треугольника (см. скрин). Внимание: DOM не будет запускаться внутри VSCode, он работает только в браузере.
<div align="center">
    <img src="./assets/code-runner-work.jpg">
</div>

### Python Environment Manager
> Пакет для автоматического форматирования кода, который поддерживает JavaScript, TypeScript, CSS и множество других языков программирования.

После установки вам потребуется настроить конфигурацию. Для этого 
- используйте сочетание клавиш `Ctrl + P` или `Command + Shift + P`
- в появившемся окне введите `>format` и выберите `Format Document`
- в первый раз вам будет предложено выбрать приложения для форматирования. Выберите `Prettier`
- в следующий раз можете запускать форматирование по сочатанию клавиш, которое написано рядом с `Format Document`

<div align="center">
    <img src="./assets/format-config.jpg">
</div>
</details>
