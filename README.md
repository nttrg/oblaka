# DEVOPS ЛАБЫ
Команда "Небесные котики" - Таргович Наталья, Крашенинникова Дарья.

# Лабораторная работа 1

Пользуясь терминалом на компьютере А перенести файл с компьютера Б на компьютер С, находящиеся в одной локальной сети. (Подсказка: вам понадобится ssh). Просьба использовать MacOS/Linux/WSL.

**Выполнение лабораторной работы**:

1. Убедились, что все три компьютера находятся в одной локальной сети и имеют соединение друг с другом. Для этого на компьютерах MacOS активировали SSH-сервер, который установлен и включен по умолчанию. И также его активировали и на компьютере Windows (начиная с Windows 10, OpenSSH поставляется в качестве опциональной функции).
2. Узнали IP-адрес всех компьютеров в локальной сети.
3. Установили соединения компьютеров А и Б. Для этого в командной строке компьютера А ввели команду ```ssh dmitriy@172.28.78.253``` .
4. С помощью команды указанной ниже перенесли файл с компьютера Б на компьютер С.
   ```
   scp /Users/dmitriy/Desktop/DEVOPS_LAB1 nttrg@192.168.31.88:/Users/nttrg/Downloads
   ```
Файл успешно перенесён!

Скрины подтверждающие выполнение работы: 

 <img src="https://github.com/nttrg/oblaka/blob/main/screens/screen1.jpeg" width="600">

Перенесённый файл на компьютаре С:

 <img src="https://github.com/nttrg/oblaka/blob/main/screens/screen2.jpeg" width="600">


# Лабораторная работа 2
Написать два Dockerfile – плохой и хороший. Плохой должен запускаться и работать корректно, но в нём должно быть не менее 3 “bad practices”. В хорошем Dockerfile они должны быть исправлены. В Readme описать все плохие практики из кода Dockerfile и почему они плохие, как они были исправлены в хорошем  Dockerfile, а также две плохие практики по использованию этого контейнера.

**Выполнение лабораторной работы:**

Плохой Dockerfile:

```Dockerfile
# Использование устаревшей версии Python 2.7
FROM python:2.7

# Неоптимальное копирование файлов
COPY . /app

# Использование CMD для запуска скрипта вместо ENTRYPOINT
CMD ["python", "/app/hello.py"]

# Создаем питоновский файл
RUN echo "print('Hello, world!')" > /app/hello.py
```

Хороший Dockerfile:

```Dockerfile
# Используем официальный образ Python 3.9
FROM python:3.9

# Устанавливаем зависимости
COPY test.txt /app/test.txt
WORKDIR /app
RUN pip install --no-cache-dir -r test.txt

# Копируем исходный код
COPY . /app

# Задаем рабочую директорию
WORKDIR /app

# Запускаем приложение с помощью ENTRYPOINT
ENTRYPOINT ["python", "app.py"]
```

**Плохие практики в Dockerfile:**
1. **Использование устаревшей версии Python 2.7**: В Dockerfile_bad используется устаревшая версия Python 2.7. Это плохая практика, так как Python 2.7 больше не поддерживается и не получает обновлений безопасности. В Dockerfile_good мы исправили это, используя актуальную версию Python 3.9.

2. **Неоптимальное копирование файлов**: В плохом Dockerfile используется неоптимальный способ копирования файлов с помощью команды `COPY . /app`. Это приводит к копированию всех файлов из текущего контекста сборки в контейнер, включая ненужные файлы и директории. В хорошем Dockerfile мы исправили это, сначала копируя только файл `11.txt` , чтобы установить зависимости, а затем копируя исходный код отдельно.

3. **Использование CMD для запуска скрипта вместо ENTRYPOINT**: В плохом Dockerfile используется команда `CMD python app.py` для запуска скрипта. Это плохая практика, так как команда `CMD`  предназначена для передачи аргументов командной строки, а не для запуска приложения. В хорошем Dockerfile мы исправили это, используя команду `ENTRYPOINT` , которая позволяет явно указать, какой исполняемый файл должен быть запущен при запуске контейнера.

Скрины подтверждающие выполнение работы: 

<img src="https://github.com/nttrg/oblaka/blob/main/screens/screen4.jpeg" width="600">

<img src="https://github.com/nttrg/oblaka/blob/main/screens/scrren6.jpeg" width="600">

<img src="https://github.com/nttrg/oblaka/blob/main/screens/scrren7.jpeg" width="600">

<img src="https://github.com/nttrg/oblaka/blob/main/screens/scrren5.jpeg" width="600">

**Плохие практики при использовании контейнера:**

1. Неоптимальное использование ресурсов: Если контейнер не настроен оптимально, он может использовать лишние ресурсы, такие как CPU, память или дисковое пространство. Например, если контейнеру выделено слишком много памяти, это может привести к неэффективному использованию ресурсов хост-системы. Рекомендуется настроить контейнер с учетом требований приложения и ограничить ресурсы, если это необходимо.

2. Необновление контейнера: Если контейнер не обновляется регулярно, он может содержать уязвимости безопасности или устаревшие зависимости. Рекомендуется регулярно обновлять контейнеры, применяя последние исправления безопасности и версии зависимостей, чтобы минимизировать риски и обеспечить безопасность приложения.

# Лабораторная работа 3

Сделать, чтобы после пуша в ваш репозиторий автоматически собирался докер образ и результат его сборки сохранялся куда-нибудь. (например, если результат - текстовый файлик, он должен автоматически сохраниться на локальную машину, в ваш репозиторий или на ваш сервер).

**Выполнение лабораторной работы**:

1. В корневом каталоге репозитория создаём файл Dockerfile, из которого будет собираться образ, и прописываем в нём следующие команды:

```Dockerfile
FROM alpine:latest
RUN echo "Hello, world!" > /output.txt
```

Этот Dockerfile использует базовый образ Alpine Linux и внутри контейнера создает файл output.txt с сообщением "Hello, world!".

2. Для автоматической сборки образа настроим GitHub Actions. Для этого в репозитории создаём новый файл с названием .github/workflows/docker-build.yml. и добавляем следующий код:

```
name: Docker Build

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Check Out Repository
      uses: actions/checkout@v2

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v1

    - name: Build Docker Image
      run: docker build -t my-docker-image .

    - name: Save Output File
      run: docker run --rm my-docker-image cat /output.txt > output.txt

    - name: Commit Changes
      run: |
        git config --global user.email "wwwnataby@gmail.com"
        git config --global user.name "nttrg"
        git add output.txt
        git commit -m "Add output.txt [skip ci]"
        git push --set-upstream origin HEAD:${GITHUB_REF#refs/heads/} --force
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
Этот workflow будет срабатывать при каждом пуше в ветку main. Он собирает Docker образ, запускает контейнер для сохранения файла output.txt из контейнера, коммитит изменения и пушит их обратно в репозиторий.

3. Проверяем выполнение. После пуша в репозиторий во вкладке Actions можно увидеть, что сборка прошла успешно. И с репозитории появился файл output.txt с сообщением "Hello, world!"
   
Скрины подтверждающие выполнение работы: 

<img src="https://github.com/nttrg/oblaka/blob/main/screens/screen8.png" width="600">
<img src="https://github.com/nttrg/oblaka/blob/main/screens/screen9.png" width="600">
<img src="https://github.com/nttrg/oblaka/blob/main/screens/screen11.png" width="600">
<img src="https://github.com/nttrg/oblaka/blob/main/screens/screen10.png">




