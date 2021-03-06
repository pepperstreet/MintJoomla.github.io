---
layout: doc
title:  "Создание шаблонов - основы"
date:   2013-07-16 18:53:38
tags: templates developer
---

Если Вы умеете работать с шаблонами Cobalt, перед Вами открываются неограниченные возможности. Каждый, кто понимает эту простую концепцию, кушает бананы. Все, что он может сказать:

> WOW! Теперь я могу делать все что захочу!

Но сначала надо научиться. И это займет некоторое время. Но мы поможем Вам пройти этот путь. И даже если у Вас возникнут вопросы, на которые мы не ответили в этой статье, мы поможем Вам и ответим на любой из них на нашем [форуме поддержки](http://support.mintjoomla.com/ru).

## 1. Что такое шаблоны Cobalt?

Шаблоны Cobalt это система, позволяющая Вам устанавливать различные шаблоны вывода или стили для каждой _секции_ или _типа контента_ или _поля_.

#### Настройки шаблонов в Типе контента

![](/assets/img/screenshots/typetmpl.png)

#### Настройки шаблонов в Разделе

![](/assets/img/screenshots/sectiontmpl.png)

При таком подходе каждый раздел, статья, комментарий или другой отображаемый блок может выглядеть по разному. В то же время, все изменения сохраняются при обновление самого Cobalt.
Маленький значок шестеренки позволяет Вам устанавливать параметры шаблонов. Также у Вас есть возможность создавать собственные шаблоны.

## 2. Требования

Для управления шаблонами Вам не обязательно быть экспертом.

- Знание CSS/HTML - **Любой уровень** (но естественно чем больше вы знаете тем больше вы сможите)
- Знание [Twitter Bootstrap](http://twitter.github.io/bootstrap/index.html). Это набор стилей которые использует сегодня Joomla серии 3. Вам будет гораздо легче верстать если вы изучите возможности этого фреймворка. Это не должно зянять больше 20 минут.
- Знание PHP - **Начальный уровень** (некоторые приемы программирования требуют более глубоких знаний, но для базового редактирования шаблонов начального уровня более чем достаточно). Под начальным я понимают что вы хотя бы можите отличить кусок PHP кода от HTML.

  То есть сможите понять смысл вот такого выражения

          <h2><?php echo $item->title; ?></h2>

  Это выражение просто выводит на экран заголовок статьи. Если это не трудно для Вас, можете продолжать чтение.

## 3. Создание копии шаблона

Разработку любого шаблона необходимо начинать с создания копии уже существующего шаблона. Это очень важный шаг для сохранения изменений при следующем обновлении Cobalt. Если вы будите править существующий шаблон то рискуете потерять ваши правки так как при установке он будет опять перезаписан.

- (1) Откройте менеджер шаблонов Cobalt.
- (2) (3) Выберите шаблон, который подходит Вам больше всего. Обычно есть только один _default_ шаблон по умолчанию, однако для списка статей и для индекса категории есть несколько шаблонов. Если Вам необходим табличный шаблон, копируйте _deafult_. Если Вам нужен шаблон, больше похожий на блог, копируйте _simple_list_.
- (4) Нажмите кнопку _Копировать/Переименовать_ на панели управления.
- (5) (6) Введите новое имя шаблона и нажмите кнопку _Копировать_.

  <div class="alert">Помните, новое имя шаблона будет частью файлового имени шаблона. Поэтому используйте только символы `a-z` и `_`.  Используйте только маленькие буквы.</div>

  После обновления страницы Вы увидите новый шаблон в списке.
- (7) Если Вы копируете шаблон из _Список статей_, также необходимо изменить имя шаблона. Потому что это имя в дальнейшем может быть использовано в переключателе шаблонов на frontend, если Вы используете больше 1 шаблона для раздела. Введите имя в поле _Изменить метку_ и нажмите кнопку _Изменить метку_.

![](/assets/img/screenshots/copytmpl.png)

## 4. Где расположены файлы шаблонов

Ниже описаны пути, где будут сохранены Ваши новые шаблоны. * - имя, которые Вы дадите шаблону при его копировании.

- Список статей - `/components/com_cobalt/views/records/tmpl/default_list_*`
- Индекс категории - `/components/com_cobalt/views/records/tmpl/default_cindex_*`
- Основная разметка - `/components/com_cobalt/views/records/tmpl/default_markup_*`
- Полный вид статьи - `/components/com_cobalt/views/record/tmpl/default_record_*`
- Комментарии - `/components/com_cobalt/views/record/tmpl/default_comments_*`
- Форма - `/components/com_cobalt/views/form/tmpl/default_form_*`
- Выбор категории - `/components/com_cobalt/views/form/tmpl/default_category_*`

## 5. Файлы шаблонов

Каждый шаблон может иметь эти файлы. Возьмем для примера шаблон `default_record_default.php`.
Вы можете создать следующие файлы

- `default_record_default` - папка, в которой хранятся все дополнительные файлы Вашего шаблона. Вы должны использовать эту папку, если хотите, чтобы все необходимые файлы были скопированы упаковщиком Cobalt.
- `default_record_default.php` - сам файл шаблона.
- `default_record_default.css` - содержит таблицы стилей CSS шаблона. Подключается автоматически.
- `default_record_default.js` - содержит java скрипты. Подключается автоматически.
- `default_record_default.png` - маленькая картинка шаблона для предварительного просмотра в менеджере шаблонов. Как правило, размер изображения не превышает 300x300 px. Но Вы можете сделать его больше.
- `default_record_default.xml` - содержит информацию об авторе и параметрах шаблона. Как использовать параметры, я покажу позже.

## 6. Параметры шаблонов

Мы посвятили статью о том [как работать с парамтерами шаблонов](/ru/cobalt/create-templates-params).

## 7. Настройка шаблонов

Так как каждый вид шаблона имет свои особенности мы создали отдельные статьи как редактировать шаблоны.

- [Работа с шаблономи статьи или списка статей](/ru/cobalt/create-templates-articles)
- [Работа с шаблономи форм](/ru/cobalt/create-templates-forms)
- [Работа с шаблономи полей](/ru/cobalt/create-templates-fields)

## 8. Создание установочного пакета

Существует 2 способа создания установочного пакета. Первый очень простой - просто упакуйте все файлы в zip-архив. Если Вы хотите упаковать несколько шаблонов, Вы можете организовать структуру вложенных папок. Но на самом деле не важно, как Вы их упаковали. Установщик на основании имени файла скопирует его в правильное место.

Такой пакет будет хорош только при установке через менеджер шаблонов.

Если Вы хотите устанавливать Ваш пакет через установщик Joomla, Вам необходимо изучить, как это делается. Это не входит в тему урока.