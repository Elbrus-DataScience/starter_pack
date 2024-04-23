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
<summary>2. Git</summary>
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
    
  При чистой установке Ubuntu 22.04 `git` по умолчанию не поставляется, как и для macOS. Можно проверить это в терминале (сочетание клавиш для linux `Ctrl + Alt + T`, на macOS - ищите `Terminal` (но рекомендую [установить](https://iterm2.com) `iTerm2` и использовать его) через Spotlight): напишите в новом окне `git`. Если терминал вам говорит, что такого пакета нет - идём его устанавливать.
[Следуйте инструкции для вашей ОС](https://git-scm.com/downloads)
  </details>
</details>

<details>
<summary>3. GitHub </summary>
  <br>
    
  <details>
  <summary>3.1 Что такое GitHub?</summary>
  <br>

  Для начала посмотри [лекцию по github](https://youtu.be/4TRClQ7rttw)  
  
  GitHub - это [cистема управления версиями](https://ru.wikipedia.org/wiki/Система_управления_версиями) с социальной составляющей. В соцсети вы выкладываете фотографии, а тут исходный код. Это ещё и самая большая площадка для opensource     проектов. Веб-сервис основан на [системе](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) контроля версий [Git](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F). Ну и конечно, вы можете сделать свою гитхаб страницу своим [*резюме*](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme).
  </details>

 <details>
 <summary>3.2 Настройка доступа по SSH</summary>
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
  <summary>3.3 Проверка настройки SSH или твой первый Fork</summary>
  <br>
  
  Когда ваша система уже настроена, получен и подключен SSH-ключ, вам ничего не мешает создать копию этого репозитория у себя в аккаунте. Нужно лишь нажать на кнопку `Fork` сверху справа на главной странице репозитория - `https://github.com/Elbrus-DataScience/starter_pack`
  
  Теперь можно перейти на свою страницу c репозиториями `https://github.com/USER?tab=repositories`, *здесь и далее* `USER` – ваш ник в GitHub. Второй вариант - вы кликаете на фото профиля в правом верхнем углу и переходим во вкладку `Your profile` или `Your repositories` для доступа к странице аккаунта и репозиториев соответственно.
  
  - переходим на страницу вашего форка (в поле ввода браузера должно быть `https://github.com/USER/starter_pack`)  
  - здесь нажимаем на *зелёную* кнопку <span style="color: green;">**Code**</span>  
  - выбираем вкладку <span style="text-decoration:underline">**SSH**</span>  
  - *копируем* ссылку на репозиторий (она должна быть такого вида: `git@github.com:USER/starter_pack.git`)  
  
  </details>

  <details>
  <summary>3.4 Дополнительные материалы</summary>
  <br>
  
  📑 Инструкция по генерации [ключа SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
  📑 Статья про fork на [GitHub](https://docs.github.com/en/get-started/quickstart/fork-a-repo)  
    
  </details>
</details>


</details>

<details>
<summary>4. Conda</summary>
  <br>
  
  <details>
  <summary>Что такое Conda?</summary>
  <br>
  **Окружения** или **виртуальные среды** - они необходимы для корректной работы. Как правило, для **каждого** рабочего проекта создаётся своя изолированная среда/окружение, куда устанавливаются необходимые *только для этого проекта пакеты/библиотеки*, чтобы не возникало конфликтов разных версий библиотек и можно было корректно отслеживать перечень зависимостей для проекта. 

В процессе обучения мы будем использовать [сonda](https://docs.conda.io/projects/conda/en/latest/) для создания и управления окружениями Python. Это один из вариантов, например, [здесь](https://python-scripts.com/virtualenv) описана работа с окружениями другого инструмента - [virtualenv](https://virtualenv.pypa.io/en/latest/). Можно использовать и его, но поговорим об этом ниже.  

  </details>

  <details>
  <summary>Установка  Conda</summary>
  <br>
      
*Напоминаем, что мы [рекомендуем](linux.md) установить Ubuntu, если у вас Windows компьютер.*

**Conda** - менеджер пакетов для Python. Как и [pip](https://pypi.org/project/pip/) - который по умолчанию.

Мы выбрали минимальную версию установщика conda, так называемую [miniforge](https://github.com/conda-forge/miniforge). Выбор пал на эту версию, т.к. при использовании этого варианта все пакеты работают корректно у всех, в том числе с процессорами Apple silicon. Тем самым воспроизводимость условий будет максимальна. 

Для установки будет необходимо перейти на git репозиторий [miniforge](https://github.com/conda-forge/miniforge) и скачать соответствующую версию установщика для своей операционной системы. Затем установить его. Ниже пример для linux.

### Linux
Если у вас компьютер с процессором **x86_64**, а это в 99% случаев, любой **не** Apple компьютер, то выбирайте эту версию для скачивания и следуй дальнейшим шагам:
- скачайте по ссылке [Miniforge3-Linux-x86_64](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh), файл сохранится где-то в `Downloads` или  в `Загрузки`
- в терминале перейдите папку, где сохранился файл и запустите команды
    ```
    chmod +x Miniforge3-Linux-x86_64.sh
    sh Miniforge3-Linux-x86_64.sh
    source ~/miniforge3/bin/activate 
    ```

- если при перезапуске терминала после установки miniforge нет "префикса" `(base)` перед именем пользователя, то чтобы всегда запускалась эта среда, можно открыть файл `.bashrc` и добавить в конце файла строку `source ~/miniforge3/bin/activate`
- проверить доступные вам среды можно по команде `conda env list`, подробнее про управление средами в conda [здесь](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

...

### macOS
Если компьютер от **Apple**, необходимо [уточнить](macOS.md) соответствующую версию для вашего процессора и скачать нужный установщик [miniforge](https://github.com/conda-forge/miniforge)   
Дальше по аналогии с инструкцией по установке на Linux (меняем `Miniforge3-Linux-x86_64.sh` на название скачанного файла)

  </details>
</details>

<details>
<summary>5. Jupyter notebook/lab</summary>
  <br>
  
  <details>
  <summary>Что такое Jupyter notebook/lab?</summary>
  <br>

  [Лекция по jupyter notebook / Lab](https://youtu.be/qPPAJ9BHvng)

  Один из основных инструментов работы, позволяющий разрабатывать и представлять результаты работы в Data Science. Использует интерактивный Python на локальном компьютере. Notebook - это "блокнот", который соединяет код и его визуализацию в ячейках - исполняемых и для разметки. 
  
  </details>

  <details>
  <summary>Установка  Jupyter notebook/lab</summary>
  <br>

  1. Заходим [сюда](https://jupyter.org/install)
  2. Выбираем версию либо notebook либо lab и устанавливаем
  

  </details>

  ## Материалы
- 🐍 [Jupyter Project Documentation](https://docs.jupyter.org/en/latest/)
- 🐍 [Документация по Lab](https://jupyterlab.readthedocs.io/en/stable/)
- 📝 [Jupyter Notebook для начинающих](https://webdevblog.ru/jupyter-notebook-dlya-nachinajushhih-uchebnik/)
- 
</details>


<details>
<summary>6. VS Code</summary>

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

</details>

### Итог

На этом установка необходимого ПО завершена.
Необходимо переходить к инструкциям по настройке VS Code и использование GitHub


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
