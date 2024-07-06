Этот проект представляет собой пример простого веб-приложения на Flask с использованием PostgreSQL в качестве базы данных. В приложении реализована обработка данных о вакансиях и их сохранение в базу данных.

### Файлы и описание

- **Dockerfile**: Файл для создания Docker образа с настройками и зависимостями.
- **docker-compose.yml**: Файл для описания многоконтейнерного приложения с настройками сервисов и объединением их в одну сеть.
- **requirements.txt**: Файл со списком зависимостей Python.
- **app.py**: Основной скрипт Flask приложения.
- **init.sql**: SQL скрипт для инициализации базы данных.
- **templates/**: Директория с шаблонами Jinja2 для Flask.
  - **index.html**: Основной HTML шаблон.
- **static/**: Директория со статическими файлами (CSS, JS и т.д.).
  - **style.css**: Файл стилей.

### Установка и запуск

#### Зависимости

Прежде чем начать, убедитесь, что у вас установлены Docker и Docker Compose.

#### Шаги для установки и запуска:
  #### 1)Клонирование репозитория:
  '''bash
    git clone https://github.com/Wex187/practice.git
  ```
    cd repository-name(куда вы будете сохранять)

  #### 2)Изменение параметров:
  в app.py подставьте ссответствующие значения для бд
  ```python
  def connect_db():
      return psycopg2.connect(
          host=os.getenv('DATABASE_HOST', 'localhost'),
          user="postgres",
          password="12365477Suka",
          database="vac",
      )
  ```

  #### 2)Создание и запуск Docker контейнеров:
  ```bash
    docker-compose up --build
  ```
    Эта команда соберет и запустит все необходимые контейнеры, включая веб-приложение и базу данных PostgreSQL.

  #### 3)Инициализация базы данных:
    При первом запуске Docker контейнер с PostgreSQL автоматически выполнит инициализацию базы данных с помощью файла init.sql. Для настройки доступа к базе данных, убедитесь, что вы задали следующие переменные окружения в файле docker-compose.yml:
```yaml
services:
  db:
    environment:
      POSTGRES_DB: vac
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: ваш_пароль
```


  #### 4)Запуск веб-приложения:
    После успешного запуска Docker контейнеров, веб-приложение будет доступно по адресу http://127.0.0.1:5000.
  

#### Использование:
  #### 1)Открытие приложения:
    Откройте браузер и перейдите по адресу http://127.0.0.1:5000.

  #### 2)Добавление данных:
    На главной странице приложения вы можете добавить данные о вакансии, заполнив соответствующие поля и нажав кнопку "Сохранить".

  #### 3)Просмотр данных:
    Добавленные данные о вакансиях будут сохранены в базе данных PostgreSQL и могут быть просмотрены на странице приложения.

#### Заключение:
  Этот README файл предоставляет основные инструкции по установке, запуску и использованию вашего Flask приложения с использованием Docker контейнеров и PostgreSQL. Если у вас возникнут вопросы или проблемы, пожалуйста, обратитесь к документации Docker и Flask, либо задайте вопрос в репозитории проекта.

  
