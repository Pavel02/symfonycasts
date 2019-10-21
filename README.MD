## Развертывание проекта DEV окружение

* Копируем файл ``.env`` в ``.env.local`` и указываем актуальные значения перменных окружения.

* Поднимаем контейнеры
```bash
docker-compose up -d
```

* Добавляем в /etc/hosts новую запись ``127.0.0.1       the-space-bar.localhost``


* Устанавливаем зависимости проекта 
```bash
docker-compose exec php composer install

```

* Создаем схему БД
```bash
docker-compose exec php bin/console doctrine:migrations:migrate
```


* Загружаем фикстуры
```bash
docker-compose exec php bin/console doctrine:fixtures:load
```

Проект станет доступен в браузере по ``http://the-space-bar.localhost``