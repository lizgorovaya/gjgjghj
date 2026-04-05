# Cloud Storage (Облачное хранилище файлов)

## Описание проекта
Веб-приложение для загрузки, хранения и управления файлами пользователей.

Функциональность:
- загрузка файлов на сервер
- удаление и переименование файлов
- поиск файлов
- управление пользователями
- возможность делиться файлами с другими пользователями
- работа с папками

Проект реализован с использованием архитектуры MVC и REST API.

---

## Технологии
- PHP 8.1+
- MySQL 5.7+
- PDO
- Встроенный PHP сервер или Apache

---

## Требования
- PHP >= 8.1
- MySQL >= 5.7
- Git

---

## Установка и запуск

1. Клонировать репозиторий:
'git clone https://github.com/username/project.git'

2. Перейти в папку проекта:
'cd project'

3. Создать базу данных в MySQL

4. Импортировать файл db.sql:

'mysql -u root -p fproject < db.sql'

5. Настроить подключение к базе данных в файле:

'/Core/Db.php'

6. Запустить сервер: 

'php artisan serve'


---

## AUTH

### POST /login
Авторизация пользователя

{
"email": "test@test.com
",
"password": "123456"
}

---

### GET /logout
Выход пользователя

---

### POST /reset_password
Сброс пароля

{
"email": "test@test.com
"
}


---

## USERS

### GET /users/list
Получить список пользователей

---

### GET /users/get/{id}
Получить пользователя по ID

---

### GET /user/search/{email}
Поиск пользователя по email

---

### PUT /users/update
Обновление пользователя

{
"id": 1,
"email": "new@mail.com
"
}


---

## FILES

### GET /files/list?userId=1
Получить список файлов пользователя

---

### GET /files/get/{id}
Получить файл по ID

---

### POST /files/add
Загрузка файла

form-data:
- file: файл  
- userId: 1  

---

### PUT /files/rename
{
"userId": 1,
"fileId": 1,
"newName": "file.txt"
}


---

### DELETE /files/remove/{id}
Удаление файла

---

## FILE SHARING

### GET /files/share/{id}
Получить список пользователей с доступом

---

### PUT /files/share/{id}/{user_id}
Предоставить доступ к файлу

---

### DELETE /files/share/{id}/{user_id}
Удалить доступ к файлу

---

## DIRECTORIES (Folders)

### POST /directories/add
{
"name": "folder1",
"userId": 1
}


### PUT /directories/rename

{
"id": 1,
"name": "new_folder"
}


---

### GET /directories/get/{id}
Получить папку

---

### DELETE /directories/delete/{id}
Удалить папку

---

## Архитектура проекта

Проект реализован по следующим принципам:
- MVC (Model-View-Controller)
- SOLID
- Repository Pattern
- Service Layer

Структура проекта:
- Controllers — обработка HTTP-запросов
- Services — бизнес-логика
- Repositories — работа с базой данных
- Core — базовые классы (App, Router, Request, Response, Db)

---

## Примечание

Проект выполнен в учебных целях.
