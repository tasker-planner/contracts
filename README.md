# contracts

Единый источник правды по всем контрактам Task Tracker: документация API,
`.proto`-файлы и форматы сообщений Kafka. Сервисы подключают сгенерированный
из этих файлов Go-код как модуль `github.com/tasker-planner/contracts`.

## Proto

| Файл | Сервис | Кто клиент |
|------|--------|------------|
| [proto/auth/v1/auth.proto](proto/auth/v1/auth.proto) | AuthService — выдача/проверка JWT | gateway |
| [proto/users/v1/users.proto](proto/users/v1/users.proto) | UserService — регистрация, проверка пароля | gateway |
| [proto/tasks/v1/tasks.proto](proto/tasks/v1/tasks.proto) | TaskService — CRUD задач, ежедневный отчёт | gateway, k8s CronJob (`report`) |
