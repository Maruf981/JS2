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

### 4. Добавление и удаление элементов

#### Создание элементов:
- `document.createElement('tag')` — создает новый элемент.

#### Вставка элементов:
- `parent.appendChild(child)` — добавляет элемент в конец родителя.
- `parent.insertBefore(newElement, referenceElement)` — вставляет элемент перед указанным элементом.

#### Удаление элементов:
- `parent.removeChild(child)` — удаляет дочерний элемент.

#### Пример:
```javascript
// Создать новый элемент
const newElement = document.createElement('p');
newElement.textContent = 'Новый параграф';

// Добавить его на страницу
const container = document.getElementById('container');
container.appendChild(newElement);

// Удалить элемент
container.removeChild(newElement);
```

### 5. События в DOM

DOM позволяет обрабатывать пользовательские действия через события:

- `onclick` — клик мыши.
- `oninput` — ввод данных.
- `onmouseover` — наведение мыши.

#### Пример:
```javascript
const button = document.querySelector('button');

button.addEventListener('click', () => {
    alert('Кнопка нажата!');
});
```

### Пример работы с DOM

```javascript
// Изменить текст заголовка
document.getElementById('header').textContent = 'Привет, мир!';

// Создать новый элемент
const newDiv = document.createElement('div');
newDiv.textContent = 'Это новый div';
document.body.appendChild(newDiv);

// Обработать событие
document.querySelector('button').addEventListener('click', () => {
    console.log('Кнопка нажата!');
});
```

### Примечания:
- DOM является основной частью взаимодействия JavaScript с HTML.
- Изменения в DOM сразу отображаются на странице.
- Для работы с DOM важно учитывать производительность при большом количестве узлов.


## `innerHTML` в JavaScript

### Описание
`innerHTML` — это свойство DOM, которое позволяет получить или установить HTML-содержимое элемента. Оно может быть использовано для вставки или извлечения HTML-кода внутри элемента.

- **Получение содержимого**: `element.innerHTML` — возвращает HTML-содержимое элемента как строку.
- **Установка содержимого**: `element.innerHTML = 'HTML-код'` — заменяет текущее содержимое элемента на указанный HTML-код.

### Пример:
```javascript
// Получить HTML-содержимое элемента
const div = document.getElementById('myDiv');
console.log(div.innerHTML); // Выведет текущее содержимое

// Изменить HTML-содержимое элемента
div.innerHTML = '<p>Новый параграф</p>';
```

## Важные замечания о `innerHTML`

### Безопасность:
Присваивание значения `innerHTML` может быть опасным, если вставляемый контент поступает от ненадежных источников (например, от пользователей), так как это может привести к уязвимостям, связанным с XSS-атаками (Cross-Site Scripting).

### Использование с осторожностью:
Частое использование `innerHTML` может негативно сказаться на производительности, так как оно заставляет браузер перерасчитывать все DOM-дерево и перерисовывать страницу.

### Динамическое добавление элементов:
`innerHTML` заменяет все содержимое элемента, включая вложенные элементы, поэтому при его использовании важно учитывать, что удалятся все предыдущие узлы и события, привязанные к ним.

### Пример с безопасным вставлением HTML:
Для предотвращения XSS атак можно использовать методы, такие как `textContent` или другие безопасные способы вставки данных, если не требуется обработка HTML.

```javascript
// Пример безопасного добавления текста
const div = document.getElementById('myDiv');
const userInput = "<script>alert('XSS')</script>"; // Потенциально опасно
div.textContent = userInput; // Отобразится как текст, а не выполнится как HTML
```
### Заключение:
`innerHTML` — мощный инструмент для работы с содержимым HTML-элементов, но требует осторожности при его использовании, особенно в контексте безопасности.

## Работа с атрибутом style в JavaScript

### Что такое `style`?

`style` — это объект, который позволяет программно изменять CSS-стили для элемента на странице. Он представляет собой коллекцию всех инлайновых стилей элемента.

### Использование `style`

Вы можете изменять стиль элемента, обращаясь к его свойствам через объект `style`. Каждый стиль элемента можно изменить как свойство этого объекта.

#### Пример:
```javascript
const element = document.getElementById('myElement');

// Изменить цвет фона
element.style.backgroundColor = 'blue';

// Изменить шрифт
element.style.fontSize = '20px';

// Изменить отступы
element.style.margin = '10px';
```

## Важные моменты:

1. **Свойства стилей**: Свойства, изменяемые через `style`, должны быть написаны в camelCase. Например, для `background-color` будет `backgroundColor`.

2. **Инлайновые стили**: Когда вы используете `style` в JavaScript, изменения касаются только инлайновых стилей, которые определены непосредственно в атрибуте `style` элемента. Если стиль задан в CSS-файле, изменения через `style` не затронут его.

3. **Объект `style`**: Он не может быть использован для чтения стилей, примененных через внешние или внутренние CSS-стили. Для этого следует использовать метод `getComputedStyle`.

### Пример работы с `getComputedStyle`:
Если вы хотите получить вычисленные стили элемента (например, значения, определенные в CSS, а не инлайновые стили), используйте `getComputedStyle`:
```javascript
const element = document.getElementById('myElement');
const computedStyles = window.getComputedStyle(element);

console.log(computedStyles.backgroundColor); // Получит вычисленный цвет фона
```

### Примечания:
- Изменение стилей через `style` применяется только к конкретному элементу, а не ко всем элементам, к которым применяется общий класс.
- Использование `style` может быть полезно для динамического изменения внешнего вида элемента, но важно помнить, что это изменяет только инлайновые стили.