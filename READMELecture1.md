# BOM (Browser Object Model) в JavaScript

BOM (Browser Object Model) — это интерфейс, предоставляемый браузером для взаимодействия с окружающей средой веб-страницы. Он включает объекты, методы и свойства, позволяющие работать с окнами, историей браузера, закладками и экраном пользователя.

---

## Основные возможности BOM

### 1. **`window`**
Главный объект BOM, представляющий окно браузера.

- **Методы:**
  - `alert()` — выводит всплывающее сообщение.
  - `confirm()` — отображает диалог подтверждения.
  - `prompt()` — позволяет пользователю ввести данные.

- **Свойства:**
  - `window.innerWidth`, `window.innerHeight` — ширина и высота окна.
  - `window.location` — информация о текущем URL.

### 2. **`document`**
Объект для доступа к содержимому веб-страницы (связан с DOM — Document Object Model).

### 3. **`navigator`**
Объект с информацией о браузере и устройстве.

- **Свойства:**
  - `navigator.userAgent` — строка, идентифицирующая браузер.
  - `navigator.language` — текущий язык браузера.

### 4. **`screen`**
Объект для получения данных о параметрах экрана устройства.

- **Свойства:**
  - `screen.width`, `screen.height` — разрешение экрана.
  - `screen.availWidth`, `screen.availHeight` — доступная область экрана.

### 5. **`history`**
Объект для управления историей браузера.

- **Методы:**
  - `history.back()` — переход на предыдущую страницу.
  - `history.forward()` — переход на следующую страницу.

### 6. **`location`**
Объект для работы с URL текущей страницы.

- **Свойства:**
  - `location.href` — текущий URL.
  - `location.hostname` — имя хоста.

- **Методы:**
  - `location.reload()` — перезагружает страницу.

---

## Пример использования BOM:

```javascript
// Работа с окном
console.log(window.innerWidth); // Ширина окна
console.log(window.location.href); // URL текущей страницы

// Показать сообщение
alert('Привет, мир!');

// Информация о браузере
console.log(navigator.userAgent); // Тип браузера

// Перезагрузка страницы
location.reload();
```



# DOM (Document Object Model) в JavaScript

DOM (Document Object Model) — это интерфейс, который представляет HTML-документ в виде дерева объектов. С помощью DOM JavaScript может динамически изменять содержимое, структуру и стиль веб-страницы.

---

## Основные возможности DOM

### 1. **Дерево DOM**
Каждый элемент HTML представляется узлом в дереве. Узлы бывают следующих типов:
- **Элемент**: теги HTML, такие как `<div>`, `<p>`, `<a>`.
- **Текст**: текстовое содержимое узлов.
- **Атрибут**: такие как `class`, `id`, `src`.

---

### 2. **Доступ к элементам**

#### Методы для поиска элементов:
- `document.getElementById('id')` — ищет элемент по `id`.
- `document.getElementsByClassName('class')` — ищет элементы по классу.
- `document.getElementsByTagName('tag')` — ищет элементы по тегу.
- `document.querySelector('selector')` — возвращает первый элемент по CSS-селектору.
- `document.querySelectorAll('selector')` — возвращает все элементы по CSS-селектору.

#### Пример:
```javascript
// Найти элемент по id
const header = document.getElementById('main-header');
console.log(header);

// Найти все элементы с классом
const items = document.getElementsByClassName('item');
console.log(items);
```
 ### 3. Изменение элементов

#### Изменение текста:
- `element.textContent` — изменяет текстовое содержимое элемента.
- `element.innerHTML` — изменяет HTML внутри элемента.

#### Изменение атрибутов:
- `element.setAttribute('attribute', 'value')` — добавляет или изменяет атрибут.
- `element.getAttribute('attribute')` — получает значение атрибута.
- `element.removeAttribute('attribute')` — удаляет атрибут.

#### Пример:
```javascript
// Изменить текст элемента
const title = document.getElementById('title');
title.textContent = 'Новый заголовок';

// Изменить атрибут
const image = document.querySelector('img');
image.setAttribute('src', 'new-image.jpg');
```
