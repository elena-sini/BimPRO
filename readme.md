# gulp-template
Сборка gulp + webpack
---

## **В корне следующие файлы и папки:**

1. Папка **config** — содержит папки и файлы для настройки работы сборщиков, а также файлы с отдельными задачами.
2. Папка **src** — содержит исходные файлы и папки проекта.

---
* Файл **package.json** — файл содержащий команды запуска сборщиков, информацию об установленных плагинах и их версиях (можно редактировать при необходимости). А также прочую информацию о об авторе и версии шаблона.
* Файл **gulpfile.js** — главный файл сборщика GULP. Содержит подключения различных задач и сценарии их выполнения (можно редактировать при необходимости)
* Файл **.editorconfig** — для настроек кода во всем проекте (отступы, строки и т.п.)
* Файл **.gitignore** — для настройки исключений при пушинге на guthub
* Файл **.htmlhintrc** — для настроек и правил html-файлов

## **Содержимое папки src:**

1. Папка **files** — все файлы из этой папки будут скопированы в папку с результатом (dist/files)
	- папка **favicon** — туда складывать файлы фавиконок из архива, скачанного с **[сайта](https://realfavicongenerator.net/)
	- папка **json** — для json-файлов
2. Папка **fonts** (пустая) — используется для подключения локальных и иконочных шрифтов
3. Папка **html** — содержит .HTM файлы, которые подключаются в HTML файлы страниц (например в home.html). Тут можно создавать свои подключаемые файлы
4. Папка **svgicons** (пустая) — используется для создания SVG спрайта
5. Папка **scss** — содержит файлы и папки стилей сайта
6. Папка **js** — содержит файлы и папки скриптов сайта
7. Папка **img** — тут хранятся картинки проекта. Изначально, только кавер-фото шаблона
---
+ Файл **index.html** — индексная страница-содержание, она не обновляется автоматически при редактировании (при желании удалить)
+ Файл **home.html** — главная страница сайта (при желании переименовать в index.html)

---

### **Содержимое папки src/html:**

Файлы из этой папки предназначены для подключения в HTML-файлы страниц.

1. Файл **_header.htm** — подготовка для создания шапки сайта. Содержит тег <header> и ограничивающий контейнер. Изначально подключен в home.html
2. Файл **_footer.htm** — подготовка для создания подвала сайта. Содержит тег <footer> и ограничивающий контейнер. Изначально подключен в home.html
3. Файл **_head.htm** — содержит тег <head> внутри которого указаны метатеги, подключена иконка сайта, файл стилей а также тег <title> с переменной-заголовком. Изначально подключен в home.html
4. Файл **_js.htm** — предназначен для подключения общих js-файлов. Содержит подключение основного файла js/app.min.js из результата. Изначально подключен в home.html
5. Файл **_popup.htm** — подготовка для создания попапов. Содержит шаблонный, закомментированный HTML-код. Изначально подключен в home.html.
6. Файл **_pagging.htm** — подготовка для создания блока постраничной навигации. Содержит шаблонный HTML-код.

---

## **Содержимое папки src/scss:**

1. Файл **style.scss** — основной файл стилей. Содержит различные настройки и подключения других файлов.
2. Файл **common.scss** — файл стилей для общих, переиспользуемых блоков конкретного проекта. Изначально пуст и подключен в style.scss
3. Файл **base.scss** — файл базовых стилей шаблона. Содержит полезные SCSS-шаблоны и закомментированные подключения файлов с базовыми стилями различных модулей.
4. Файл **partials.scss** — файл для подключения стилей

### ПАПКА **partials**
* Файл **header.scss** — файл стилей шапки сайта. Содержит закомментированный код кнопки меню-бургера. Изначально подключен в style.scss
* Файл **footer.scss** — файл стилей подвала сайта. Изначально пуст и подключен в style.scss
    Далее в этой папке создаются файлы стилей секций страницы и подключаются в файле **partials.scss**

### ПАПКА **libs**
— содержит файлы полных (заводских) стилей различных модулей и плагинов

### ПАПКА **fonts**
— содержит файл(ы) стилей связанных со шрифтами. Содержит файл icons.scss для подключения иконочного шрифта. Также, в процессе подключения локальных шрифтов, тут появляется файл fonts.scss

### ПАПКА **core**
— содержит файл с обнуляющими стилями **null.scss**, файл с миксинами и функциями, а также файл с функцией перевода переменных цвета в rgba-формат

### ПАПКА **components**
— для копирования в эту папку необходимых файлов стилей из папки **libs**, из интернета и других. Способ копирования позволяет редактировать только нужные компоненты и не тянуть все вспомогательные файлы для подключений.

---

## **Содержимое папки src/js:**

1. Файл **app.js** — основной файл скриптов. Служит для подключения необходимого в проекте функционала и прочих настроек.
2. Папка **libs** — содержит файлы готовых дополнений, как правило, не предусмотренных для редактирования.
3. Папка **files** — содержит файлы различных модулей и прочего функционала.

---

## **Содержимое папки src/img:**
- Файл **cover.jpg** — обложка для индексной страницы
- При необходимости — создать папку **icons** для иконок

---

# ЗАПУСК СБОРКИ
- **npm i** - start
- **npm run dev** - Starts dev server
- **npm run fonts** - gulp fonts --rewrite
- **npm run sprite** - gulp sprite
- **npm run build** - gulp build --build
- **npm run zip** - gulp deployZIP --build
1