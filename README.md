# react-2023-07-24

## ДЗ

## Как делать

0. Сделать форк этого репозитория в свой аккаунт (только 1 раз в самом начале).

1. Перед выполнением ДЗ сделайте пул мастера этого репозитория себе в форк (чтобы иметь актуальный код);
2. Обновить зависимости `yarn` или `npm i`, или `pnpm`;
3. Создайте новую ветку от актуального мастера для выполнения ДЗ;
4. Выполните ДЗ в этой ветке;
5. Сделайте Pull Request этой ветки в мастер моего репозитория;
6. Напишите мне в личные сообщения дискорда ссылку на PR.

**Важно! В результате всех этих манипуляций в вашем мастере должны быть только мои комиты, все ваши комиты должны быть в отдельных ветках под каждую домашку.**

Дедлайн – 23:00 по GMT+3 за день до занятия.

## HT-1

1. Отобразить активный ресторан:
   1. Создать компонент Restaurant и отобразить его вместо имени активного ресторана на главной странице(принимает активный ресторан в пропсы);
   1. Отображает название ресторана и два компонента Menu и Reviews(их надо создать);
1. Menu:
   1. Принимает список блюд;
   1. Рисует список компонентов Dish(надо создать);
1. Dish:
   1. Принимает блюдо;
   1. Отображает инфу о блюде(произвольно, можно только название);
1. Reviews:
   1. Принимает список отзывов;
   1. Рисует список компонентов Review(надо создать);
1. Review:
   1. Принимает отзыв;
   1. Отображает инфу о отзыве(произвольно, можно только текст отыва);
1. Вынести табы в отдельный компонент Tabs(принимает список ресторанов и колбек(onTabSelect));

## HT-2

1. Добавить в компонент блюда счетчик:
   1. Рисуем две кнопки - и +
   1. По клику + увеличиваем, по клику на - уменьшаем счетчик
   1. Между кнопками сам счетчик отображаем
   1. После кнопок сумма = цена блюда \* кол-во.
2. Добавить компонент NewDish:
   1. Отображаем его в Menu после самого меню
   2. Состоит из полей Название блюда, цена блюда и ингредиенты(один инпут, вводим через запятую ингредиенты, в состоянии храним как массив строк)

## HT-3

1. Реализовать decrement;
2. Необходимо реализовать фейк авторизацию(Context):
   1. В шапке располагаем кнопку авторизоваться;
   1. По клику на кнопку она должна замениться кнопкой с именем пользователя(имя любое);
   1. По клику на имя пользователя оно заменяется кнопкой авторизации;
   1. Доступ к текущему пользователю мы должны иметь из любой точки приложения;
   1. - По клику на кнопку авторизоваться в шапке открываем модальное окно(Для этого необходимо почитать про React Portal https://react.dev/reference/react-dom/createPortal) с двумя полями(имя и фамилия) и кнопкой авторизоваться. Кнопка активна только тогда, когда заполнены оба поля. По клику на кнопку закрываем модалку и вместо кнопки в шапке рисуем кнопку с именем пользователя как и в обычном задании.

## HT-4

1. Необходимо реализовать в сторе фичи блюд, отзывов, пользователей(аналогично ресторанам).
2. Перевести модуль корзины на работу с айдишниками, а не названиями. Переписать компонент для работы с айдишками блюд(Подумать как реализовать грамотно, исполуйте пример с табами)
3. Перевести компоненты на использование данных из стора. Блюда, отзывы и пользователи в отзывах должны отображаться из стора. Использовать подход как в табах(передача айдишек и контейнеры) 1. Доработать ресторан(контейнер, получение ресторана из стора) 2. Доработать меню и блюда 3. Доработать отзывы и создать компонент и контейнер для пользователя
   4.\* Необходимо доработать авторизацию: 1. Переносим авторизацию в стор. 2. Дополнительно храним время авторизации пользователя. 3. Авторизация актуальна 10 минут. 4. Добавлять блюда в корзину может только авторизованный пользователь.

## HT-5

!!!(установить зависимости сервера и запустить сервер)!!!

1. Переписать мидлвару загрузки ресторанов на thunk(аналогично блюдам).
2. Реализовать загрузку отзывов и пользователей(используем thunk`и). Заиспользовать в контейнерах (отображаем индикатор загрузки). Подумайте о том месте, где правильно загружать те или иные данные(отзывы и пользователей).
3. Реализовать во всех thunk`ах (рестораны, блюда, отзывы, пользователи) проверку на уже загруженные данные, чтобы не грузить одни данные несколько раз.

Доп со звездочкой: 4. Необходимо реализовать модуль для хранения инфы о запросах. Необходимо хранить статус запроса. 5. реализовать thunk`у создания нового отзыва. У нас уже есть форма нового отзыва, нужно по клику на кнопку в форме(задезейблина если хоть одно поле пустое) отправлять пост запрос на бек и если он успешен добавить новый отзыв в стор.

## HT-6

1. переписать оставшиеся модули(features) на тулкит.

## HT-7

1. Перевести все оставшиеся запросы на RTKQuery.
   Доп:
1. Реализовать возможность переключать отзыв в режим редактирования.
   Переиспользовать форму нового отзыва. Около отзыва рисуем кнопку изменить, по клику отзыв переходит в режим редактирования.
   В режиме редактирования две кнопки - отмена и сохранение.
   Отмена - просто возвращает в режим просмотра.
   Сохранить - отправляет патч запрос.
   Если патч запрос удался, то нам важно правильно отобразить изменения.
1. Иметь возможность открыть в отдельном окне наше приложение. Если мы в одном окне изменили отзыв, то у другого пользователя он должен обновиться(можно не сразу).

Важно! Используем RTKQuery для основного и доп заданий.
