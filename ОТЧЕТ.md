## **ОТЧЁТ ПО ВЫПОЛНЕНИЮ ЗАДАНИЯ**

### **1. Выполненные действия:**

**1.1. Установка и базовая настройка Hugo**

На Windows 11 был установлен статический генератор сайтов Hugo версии 0.155.2. Программа была добавлена в PATH. Корректность установки подтверждена выполнением команды проверки версии.

```
C:\Users\storm>set PATH=%PATH%;C:\Hugo\bin
C:\Users\storm\Documents>hugo new site my-portfolio
```


**1.2. Инициализация проекта сайта**

В рабочей директории `C:\Users\storm\Documents\` был создан новый проект Hugo с помощью команды 
	`C:\Users\storm\Documents>cd my-portfolio`
В созданной директории инициализирован Git-репозиторий, выполнены базовые настройки Git (имя пользователя и адрес электронной почты).

```
C:\Users\storm\Documents\my-portfolio>git config user.name "el-mac51"
C:\Users\storm\Documents\my-portfolio>git config user.email "stormtornado16@gmail.com"
```

**1.3. Выбор и установка темы оформления**

Сначала была выбрана тема Toha, но из-за проблемы связанной с отсутствием bootstrap зависимостей, поэтому было решено идти по пути меньшего сопротивления и в итоге для сайта была выбрана тема Ananke. 
Тема была установлена как Git-подмодуль командой:
```bash
C:\Users\storm\Documents\my-portfolio>git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```

В конфигурационный файл `hugo.toml` внесены изменения: указано имя темы (`theme = "ananke"`), базовый URL сайта, кодировка языка.

**1.4. Создание контента сайта**

Были созданы следующие страницы:
- Главная страница (`content/_index.md`) с приветственным текстом и основной информацией
- Страница "Обо мне" (`content/about.md`) с описанием образования и опыта работы
- Страница проектов (`content/projects.md`) с описанием выполненных работ

Каждая страница создана через команду `hugo new`, после чего в файлах заполнена front matter (метаданные) и основное содержание в формате Markdown.

```
C:\Users\storm\Documents\my-portfolio>hugo new _index.md
Content "C:\\Users\\storm\\Documents\\my-portfolio\\content\\_index.md" created

C:\Users\storm\Documents\my-portfolio>hugo new content/about.md
Content "C:\\Users\\storm\\Documents\\my-portfolio\\content\\about.md" created

C:\Users\storm\Documents\my-portfolio>hugo new content/projects.md
Content "C:\\Users\\storm\\Documents\\my-portfolio\\content\\projects.md" created
```

**1.5. Локальное тестирование**

Для проверки работоспособности сайта был запущен локальный сервер разработки командой 
	`hugo server -D`. Флаг `-D` 
Сайт стал доступен по адресу: 
	`http://localhost:1313`. 

**1.6. Подготовка к публикации**

Выполнена сборка статического сайта командой `hugo`, в результате которой в директории `public` сгенерированы готовые HTML, CSS и JavaScript файлы. Все файлы проекта добавлены в индекс Git командой `git add .`

**1.7. Настройка удалённого репозитория**

На GitHub создан репозиторий `el-mac51.github.io` для размещения сайта. В локальном репозитории настроен remote `origin` с указанием URL удалённого репозитория. Был выполнен первый push с флагом `-u` для установки связи между локальной и удалённой ветками.

```
C:\Users\storm\Documents\my-portfolio>git remote add origin https://github.com/el-mac51/el-mac51.github.io.git
```

**1.8. Конфигурация GitHub Pages**

В настройках репозитория на GitHub (раздел Settings → Pages) выбрана ветка `main` в качестве источника публикации, указана корневая директория `/ (root)`. Включено принудительное использование HTTPS.

**1.9. Настройка автоматического развёртывания**

Для автоматической сборки и публикации сайта создан файл GitHub Actions workflow 
```
C:\Users\storm\Documents\my-portfolio>git add .github/workflows/hugo.yml
```
В настройках Pages источник изменён с "Deploy from a branch" на "GitHub Actions". После внесения изменений в репозиторий workflow автоматически запускается при каждом push в ветку `main`, обеспечивая непрерывную интеграцию.
### **2. Ссылки:**

**Репозиторий с исходным кодом:**  
https://github.com/el-mac51/el-mac51.github.io

**Развёрнутый сайт на GitHub Pages:**  
https://el-mac51.github.io/

### **3. Заключение:**

В ходе выполнения задания был развёрнут и настроен статический сайт-портфолио на базе генератора Hugo с использованием темы Ananke. Реализована структура из нескольких страниц с контентом, протестирована локальная разработка с автоматической пересборкой. Настроена публикация сайта на GitHub Pages с использованием GitHub Actions для автоматизации процесса сборки и развёртывания. Все требования задания выполнены.
