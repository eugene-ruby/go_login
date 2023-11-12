# Go REST API с аутентификацией JWT

Это пример простого REST API на Go, который включает в себя два эндпоинта для аутентификации и проверки JWT токена.

## Установка

1. Установите Go на вашу систему. Инструкции можно найти на [официальном сайте Go](https://golang.org/doc/install).

2. Склонируйте репозиторий:

   ```bash
   git clone https://github.com/eugene-ruby/go_login
   ```

3. Перейдите в директорию проекта:

   ```bash
   cd go_login
   ```

4. Установите зависимости:

   ```bash
   go mod download
   ```

## Запуск

1. Запустите приложение:

   ```bash
   go run main.go
   ```

2. Приложение будет запущено на `http://localhost:8000`.

## Использование

### Аутентификация

Отправьте POST запрос на `/login` с JSON телом, содержащим `username` и `password`. В ответе вы получите JWT токен.

```bash
curl -X POST -H "Content-Type: application/json" -d '{"username":"admin","password":"password"}' http://localhost:8000/login
```

### Проверка токена

Отправьте GET запрос на `/verify` с заголовком `Authorization`, содержащим JWT токен. В ответе вы получите код 200, если токен валидный, или код 401, если токен недействительный.

```bash
curl -X GET -H "Authorization: Bearer <token>" http://localhost:8000/verify
```

Замените `<token>` на фактический JWT токен, полученный в результате запроса на `/login`.

## Лицензия

[MIT](LICENSE)