Итоговое задание 9.5.4 (HW-03)
Новостной портал с проверкой прав доступа и возможностью ввода статей
разными пользователями. Добавления по заданию:
1. Подтверждение регистрации с приветственным письмом.
2. После регистрации и входа, по нажатии кнопки "Стать автором"
   появляется возможность подписаться на новостные разделы портала.
3. При добавлении новости, если пользователь подписан, приходит 
   письмо о создании новости, ее краткое содержание и ссылка на полную
   новость на портале.
4. При помощи модуля appscheduler можно выполнить еженедельную рассылку
   новостей, созданных на портале. Поскольку в условии задания не поставлено
   условие, что каждый подписчик должен получать инфомацию только по разделам,
   на которые подписан он, и новостях, который он создавал, то все подписчики
   получают полный список новостей, созданных за неделю. Рассылка работает, 
   если отдельно, кроме сервера, запущено команда 
   python manage.py runapscheduler
   *нюанс: запуск рассылки происходит не раз в неделю, т.к. ждать проверки
   выполнения задания было бы проблематично, а раз в 10 минут - т.е. каждые
   10 минут запускается задание с запросом к БД на созданные за последние 7 дней
   новости на портале и результат рассылается подписчикам. При необходимости
   интервал проверки в 10 минут легко исправить на секунды или дни в соответствии
   с документации apscheduler.

Перед запуском:
pip install django
pip install django-filter
pip install django-allauth
pip install django-apscheduler

или

pip install -r .\requirements.txt

Настройка базы сообщений загрузкой статей и созданием пользователей:
пример в файле loading_news_base_users34.txt