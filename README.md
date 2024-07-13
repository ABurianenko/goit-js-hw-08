# goit-js-hw-08

-----ДЕЛЕГУВАННЯ ПОДІЙ-----

Поширення подій (event propagation) — це термін, що описує життєвий цикл події, який має три етапи:
Занурення (capture phase).
Таргетинг (target phase).
Спливання (bubble phase).

Під час настання події обробники спочатку спрацьовують на найбільш вкладеному елементі. Потім — на його батьківському елементі, потім — вище і так далі, вгору по ланцюжку вкладеності. Цей процес називається спливання (event bubbling)

Елемент, на якому відбулася подія, називається цільовим, або вихідним. Це завжди найглибший елемент, з якого починається спливання. Він доступний як event.target.

Будь-який проміжний обробник може зупинити спливання цієї події за допомогою методів об’єкта події (event):
event.stopPropagation(),
event.stopImmediatePropagation()

Делегування подій (event delegation) полягає в додаванні одного обробника на спільного предка цих елементів.

Отже, делегування реалізується у три прості кроки.

1. Визначити спільного предка групи елементів для відстеження подій.
2. Зареєструвати на елементі-предку обробник події, яку ми хочемо відловлювати з групи елементів.
3. В обробнику використовувати event.target для вибору цільового елемента, на якому безпосередньо відбулась подія.

-----БІБЛІОТЕКИ-----

Бібліотеки — це набір попередньо написаних функцій, методів і класів, який надає розробнику готові інструменти для вирішення певних завдань.

CDN (Content Delivery Network) — це географічно розподілена мережева інфраструктура. Вона забезпечує швидку доставку контенту (такого як стилі, скрипти, зображення та інші ресурси) користувачам вебсервісів і сайтів.

Підключення JavaScript бібліотеки через CDN складається з декількох кроків.
Крок 1. Для початку зайди на сайт CDN сервісу https://www.jsdelivr.com/ і знайди необхідну бібліотеку за її ім'ям.
Крок 2. У списку результатів обери необхідну бібліотеку, клікнувши на назву. Після переходу за посиланням, ти опинишся на сторінці з інформацією про бібліотеку.
Крок 3. Скопіюй HTML-код тега script, після чого відкрий свій HTML-файл і додай посилання на скрипт бібліотеки наприкінці HTML-документа
Підключення скрипта бібліотеки має бути до підключення твого основного файлу скриптів.
Не забудь додати тегу script бібліотеки атрибут async. Це потрібно для того, щоб файл бібліотеки завантажувався якомога швидше.

У більшості офіційних документацій до бібліотек інструкції зі встановлення та підключення до проєкту найчастіше розташовані в розділах, які мають назви "Get Started", "Quick Start", "Installation", "Setup" або подібні.

Більшість документацій надає різноманітні приклади використання, які можна адаптувати для своїх потреб. Це часто зображено в розділах "Usage", "Examples", "API" або "Demo".

Дуже важливим розділом у документації до будь-якої бібліотеки є розділ, який описує її особливості та додаткові налаштування. Цей розділ може мати різні назви в різних документаціях, але найчастіше він має назву "Options", "Advanced Settings", "Configuration Options", "Advanced Usage" або "Advanced Configuration" тощо.

-----ДЕСТРУКТУРИЗАЦІЯ-----

Деструктуризація (Destructuring) — це особливий синтаксис, що дозволяє витягти значення зі структур даних, такі як об'єкти або масиви, і присвоїти їх змінним.

Після ключового слова const або let ставимо фігурні дужки, як і у випадку з оголошенням об'єкта.
Усередині дужок, через кому, вказуємо імена змінних, яким будуть задані відповідні значення властивостей деструктуризованого об’єкта.
const book = {
title: "The Last Kingdom",
author: "Bernard Cornwell",
genres: ["historical prose", "adventure"],
isPublic: true,
rating: 8.38,
};
// Деструктуризуємо
const { title, author, isPublic, rating } = book;

Коли в об'єкті немає властивості з таким ім'ям, змінній буде присвоєно undefined.
З метою уникнення присвоєння undefined під час деструктуризації неіснуючих властивостей, можна задати змінним значення за замовчуванням, використовуючи знак =. Це значення буде присвоєно тільки у випадку, коли в об'єкті відсутня властивість із таким ім'ям.

Під час деструктуризації можна перейменувати змінну, в яку розпаковується значення властивості, використовуючи :.
Для цього пишемо:
ім'я властивості, з якої хочемо отримати значення
ставимо двокрапку :
пишемо ім'я змінної, в яку необхідно помістити значення цієї властивості

-----ДЕСТРУКТУРИЗАЦІЯ МАСИВІВ-----

Деструктуризоване присвоювання можна використовувати не тільки для об’єктів, а й для масивів, але з деякими особливостями.
Замість фігурних дужок {} використовуються квадратні [].
Змінним, зазначеним у квадратних дужках [], будуть послідовно присвоюватися значення елементів масиву.

Якщо змінних оголошено більше, ніж елементів масиву, їм буде присвоєно undefined. Щоб запобігти цьому, можна вказувати значення за замовчуванням.

Деструктуризуючи масив, можна розпакувати перші необхідні елементи і присвоїти іншу частину елементів масиву змінній, використовуючи операцію ...rest.
