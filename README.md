- статика + serverless
- функции как в нетлифае

# API для сервиса развертывания
- K8s для отдельного сервака
- выполнятся будут инфраструктурные задачи
- каждая отдельная задача в своём контейнере
- в идеале добавить поддержку GITHUB ACTIONS, bitbucket
- добавить версионирование (чтобы разные версии сервиса можно было хранить, настраивать, рассматривать)
- NGINX будет использоваться для http/https ссылок (можно рецепт прочитать на Доке)
- DNS будет в виде Real-time registration сервиса (может в виде отдельного микросервиса - но пока нет)
- сертификаты TLS устанавливать придется самим (или же сделать для пользователя отдельную кнопку где он сможет это все подключить)
- lets encrypt, wildcart поддержка ssl/tls сертификатов

# API сервиса авторизации
- работает с таблицей юзеров
- можно будет создать аккаунт
- залогинился - получил JWT токен
- на всех остальных микросервисах будет лежать файл с публичным ключом для декодирования jwt (чтобы не делать лишние запросы к сервису авторизации)
- разлогиниться тоже надо будет уметь
- удаление аккаунта (пока не понятно где именно это будет возможно, в каком микросервисе)

# API для основного сервиса
- ручки для работы с FE
- запуск тасок и работа с сервисом развертывания (с ним работа через кафку будет)
- сделать принятие файлов (в виде архива) (опасная штука лучше оставить тупо ссылкой на гит)
- гит - репа должна быть публичной для начала (потом через авторизацию на гите сделаем возможность загружать и деплоить приватные)
- поработать над взаимодействием с сервисом развертывания (ожиданиями и оповещениями)