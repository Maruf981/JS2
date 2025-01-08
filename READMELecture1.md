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


### DOM Events

DOM Events (События DOM) — это механизм, который позволяет отслеживать и реагировать на действия пользователя или изменения в документе. Веб-страницы становятся интерактивными благодаря событиям, например, нажатиям кнопок, движениям мыши, загрузке страниц и другим действиям.

Основные типы событий

## 1. События мыши

- Эти события возникают при взаимодействии с мышью:

`click` — происходит при клике на элемент.

`dblclick` — двойной клик на элемент.

`mousedown` — нажатие кнопки мыши.

`mouseup` — отпускание кнопки мыши.

`mousemove` — перемещение мыши над элементом.

`mouseenter / mouseleave` — наведение/уход мыши на/с элемента.

`mouseover / mouseout` — похожи на mouseenter / mouseleave, но срабатывают, если курсор перемещается между дочерними элементами.

## 2. События клавиатуры

- Используются для отслеживания нажатий клавиш:

`keydown` — нажатие клавиши.

`keyup` — отпускание клавиши.

`keypress` — устаревшее событие для нажатия клавиши.

## 3. События формы

- Работают с элементами формы:

`submit` — отправка формы.

`change` — изменение значения поля (например, текстового поля или выпадающего списка).

`input` — ввод данных в текстовое поле.

`focus` / blur — фокусировка на элементе / потеря фокуса.

## 4. События окна

- Отслеживают изменения состояния окна или документа:

`load` — завершение загрузки страницы.

`resize` — изменение размера окна.

`scroll` — прокрутка страницы.

`unload` — уход пользователя со страницы (устарело).

## Обработчики событий

## 1. Добавление обработчиков через HTML

Пример:
```javascript
<button onclick="alert('Кнопка нажата!')">Нажми меня</button>
```
## 2. Добавление обработчиков через JavaScript

Вариант 1: Установка свойства обработчика
```javascript
const button = document.querySelector('button');
button.onclick = () => {
    alert('Кнопка нажата!');
};
```
### Вариант 2: Использование addEventListener
```javascript
const button = document.querySelector('button');
button.addEventListener('click', () => {
    alert('Кнопка нажата!');
});
```

- Отличие addEventListener:

1. Можно добавить несколько обработчиков для одного события.

2. Обработчики можно удалить с помощью removeEventListener.

3. Удаление обработчиков событий
```javascript
function handleClick() {
    alert('Кнопка нажата!');
}
button.addEventListener('click', handleClick);
button.removeEventListener('click', handleClick);
```
### Всплытие и погружение событий

1. Всплытие (Event Bubbling)

Событие сначала происходит на целевом элементе, а затем поднимается вверх по дереву DOM.
```javascript
<div onclick="alert('DIV')">
    <button onclick="alert('BUTTON')">Нажми</button>
</div>
```
При клике на кнопку сначала выполнится событие кнопки, затем событие родительского элемента (div).

2. Погружение (Event Capturing)

- Событие идет от корневого элемента (document) к целевому элементу.

- Чтобы использовать погружение:
```javascript
element.addEventListener('click', handler, true); // true включает фазу погружения
```
Предотвращение действия по умолчанию

- Для отмены действия браузера:
```javascript
const link = document.querySelector('a');
link.addEventListener('click', (event) => {
    event.preventDefault(); // Отключает переход по ссылке
    alert('Действие отменено');
});
```
Остановка всплытия

- Для остановки всплытия события:
```javascript
button.addEventListener('click', (event) => {
    event.stopPropagation();
    alert('Всплытие остановлено');
});
```
### Полезные свойства события

`event.type` — тип события (например, click).

`event.target` — элемент, на котором произошло событие.

`event.currentTarget` — элемент, на котором висит обработчик.

`event.clientX / event.clientY` — координаты курсора относительно окна.

`event.key` — клавиша, которая была нажата.

Это краткое введение в работу с событиями DOM. Их использование позволяет создавать более интерактивные и динамичные веб-приложения.


# DOM: createElement

Метод createElement используется для создания нового элемента DOM.

Синтаксис
```javascript
document.createElement(tagName);
```
tagName — имя создаваемого элемента (например, div, span, p).

### Пример использования

1. Создание и добавление элемента на страницу
```javascript
const newDiv = document.createElement('div'); // Создаем элемент <div>
newDiv.textContent = 'Привет, мир!'; // Добавляем текст
// Добавляем созданный элемент в документ
const body = document.querySelector('body');
body.appendChild(newDiv);
```
2. Добавление атрибутов
```javascript
const button = document.createElement('button');
button.textContent = 'Кликни меня';
button.setAttribute('id', 'myButton'); // Добавляем атрибут id

// Вставляем кнопку в документ
document.body.appendChild(button);
```
3. Использование классов
```javascript
const div = document.createElement('div');
div.classList.add('my-class'); // Добавляем класс

document.body.appendChild(div);
```
4. Вложенные элементы
```javascript
const ul = document.createElement('ul');
const li1 = document.createElement('li');
li1.textContent = 'Первый пункт';
const li2 = document.createElement('li');
li2.textContent = 'Второй пункт';

ul.appendChild(li1);
ul.appendChild(li2);

document.body.appendChild(ul);
```
5. Удаление элемента

Созданные элементы можно удалить с помощью метода remove:
```javascript
const element = document.getElementById('myButton');
if (element) {
    element.remove();
}
```

Метод createElement широко используется для динамического создания интерфейсов и манипуляции DOM.


# DOM Properties: classList

Свойство classList предоставляет удобный интерфейс для работы с классами элемента. Оно позволяет добавлять, удалять, переключать и проверять наличие классов у элементов.

#### Основные методы classList

1. `add`

Добавляет один или несколько классов к элементу.
```javascript
const element = document.querySelector(".my-element");
element.classList.add("new-class", "another-class");
```
2. `remove`

Удаляет один или несколько классов у элемента.
```javascript
const element = document.querySelector(".my-element");
element.classList.remove("old-class");
```
3. `toggle`

Добавляет класс, если его нет, и удаляет, если он уже есть.
```javascript
const element = document.querySelector(".my-element");
element.classList.toggle("active"); // Если "active" есть, удалит, иначе добавит.
```
Можно передать второй аргумент для явного добавления или удаления:
```javascript
element.classList.toggle("active", true); // Явно добавляет класс "active".
element.classList.toggle("active", false); // Явно удаляет класс "active".
```
4. `contains`

Проверяет, есть ли у элемента указанный класс.
```javascript
const element = document.querySelector(".my-element");
console.log(element.classList.contains("visible")); // true или false
```
5. `replace`

Заменяет один класс на другой.
```javascript
const element = document.querySelector(".my-element");
element.classList.replace("old-class", "new-class");
```
### Свойство length

Возвращает количество классов у элемента.
```javascript
const element = document.querySelector(".my-element");
console.log(element.classList.length); // Количество классов
```
Пример работы с classList

<div id="example" class="box"></div>
<script>
  const element = document.getElementById("example");

  // Добавление класса
  element.classList.add("highlight");

  // Проверка наличия класса
  if (element.classList.contains("highlight")) {
    console.log("Класс 'highlight' присутствует");
  }

  // Удаление класса
  element.classList.remove("box");

  // Переключение класса
  element.classList.toggle("active");

  // Замена класса
  element.classList.replace("highlight", "focused");

  console.log(element.classList); // Вывод всех классов элемента
</script>

Свойство classList упрощает манипуляции с классами элементов и делает код более читаемым и лаконичным.

