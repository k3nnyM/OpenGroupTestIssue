# OpenGroupTest
Тестовое задание для OpenGroup

Задание: Реализовать на golang http сервис, который будет иметь 2 endpoint-a и асинхронную обработку задач:

1й endpoint принимает на вход любой файл, создает задачу (опишется ниже) для отложенного выполнения (которая уже самостоятельно запускается когда будет возможность), и возвращает идентификатор созданной задачи.

2й endpoint будет возвращать информацию о статусе задаче. На вход будет приходить идентификатор задачи, полученный в ответе первого endpoint-a.

Описание выполняемой кодом задачи:
До начала выполнения задачи ее статус - new. Любая задача принимается к работе после произвольного искусственного таймаута.
При начале работы задачи ее статус - in_progress. На вход передается файл. После начала выполнения срабатывает таймаут (произвольный) после которого происходит записывание файла на жесткий диск. Если запись прошла успешно - статус задачи done, если запись не получилась - статус failed.
Итого у задачи может быть 4 статуса - new, in_progress, failed, done.

