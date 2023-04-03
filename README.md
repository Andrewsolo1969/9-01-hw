# Домашнее задание к занятию "`9.1. «Обзор систем IT-мониторинга»" - `Соловьёв Андрей SYS-18


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
---

## Задание 1


Создайте виртуальную машину в Yandex Cloud Compute Cloud и с помощью Yandex Monitoring создайте дашборд, на котором будет видно загрузку процессора.

Процесс выполнения
1. В окне браузера откройте облачную платформу Yandex Cloud
2. Перейдите в раздел "Все сервисы" > "Инфраструктура и сеть" > "Compute Cloud"
3. Нажмите на синюю кнопку "Создать ВМ" в правом верхнем углу окна браузера
4. Задайте имя виртуальной машины. Используйте английские буквы и цифры.
5. Выберите операционную систему Debian 11
6. Установите объём HDD равный 3ГБ
7. Выберите платформу Intel Ice Lake
8. Установите количество vCPU равное 2
9. Установите гарантированную долю vCPU равную 20%
10. Задайте количество RAM равное 1ГБ
11. Поставьте галочку "Прерываемая"
12. В разделе "Доступ" выберите сервисный аккаунт с ролью monitoring.editor. Если такого аккаунта нету, нажмите на кнопку "Создать новый". Задайте имя аккаунта английскими буквами, напротив надписи "Роли в каталоге" нажмите на знак "плюс". Прокручивая колесо мыши на себя, найдите роль monitoring.editor и нажмите на неё левой кнопкой мыши. Теперь вы сможете найти только что созданную роль в выпадающем списке аккаунтов.
13. Задайте логин учётной записи вашей виртуальной машины
14. Вставьте публичный SHH-ключ в поле SSH-ключ. Если этого ключа у вас нету, создайте его с помощью утилиты PuTTYgen
15. Поставьте галочку "Установить" в пункте "Агент сбора метрик"
16. Нажмите на синюю кнопку "Создать ВМ"

![Создание виртуальной машины](https://github.com/Andrewsolo1969/9-01-hw/blob/main/img/VM_creating.png)

Доступ на VM по SSH по ключу

![Доступ по SSH](https://github.com/Andrewsolo1969/9-01-hw/blob/main/img/SSH.png)

17. Перейдите в раздел "Все сервисы" > "Инфраструктура и сеть" > "Monitoring"
18. Нажмите на кнопку "Создать дашборд", расположенную в разделе "Возможности сервиса" > "Дашборды"
19. В открывшемся окне в разделе "Добавить виджет" нажмите на "График"
20. Перед вам предстанет конструктор запросов, выберите "Запрос А"
21. В параметре service конструктора запросов выберите Compute Cloud
22. В появившемся параметре name конструктора запросов выберите cpu_utilization
23. Поправьте диапазон времени отрисовки графика нажав на кнопку "Сейчас" в верху экрана, левее кнопок 3m, 1h, 1d, 1w, "Отменить".
24. Нажмите на кнопку "Сохранить" в правом верхнем углу экрана
25. Задайте имя дашборда, если появится окно ввода имени дашборда
26. Сделайте скриншот

![CPU utilization](https://github.com/Andrewsolo1969/8-01-hw/blob/main/img/CPU_utilization.png)

Требования к результату
- прикрепите в файл README.md скриншот вашего дашборда в Yandex Monitoring с мониторингом загрузки процессора виртуальной машины
