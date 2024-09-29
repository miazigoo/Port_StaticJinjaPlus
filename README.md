# Порт StaticJinjaPlus

Инструкцию по использованию StaticJinjaPlus см. на [GitHub StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus/tree/main)

## Как использовать:
Для запуска вам понадобится **Docker**. Инструкции по его установке ищите на официальных сайтах:

- [Get Started with Docker](https://www.docker.com/get-started/)
### Сборка на базе Ubuntu
В директории `dock_file_ubunte` лежат файлы `Dockerfile` и `requirements` .
Для сборки образа последней версии введите в терминале:
```bash
docker build -t static-jinja-plus:ubu ./dock_file_ubuntu
```
В файле `requirement` указана последняя версия StaticJinjaPlus . 
Если вам нужна определенная версия **StaticJinjaPlus**, то укажите это в файле `requirements`. Например:
```requirements
staticjinjaplus == 2.0.0
```
Если нужна определенная версия **Ubuntu**, можно использовать аргумент  `UBUNTU_VERSION`, например:
```bash
docker build --build-arg UBUNTU_VERSION=22.04 -t static-jinja-plus:ubu ./dock_file_ubuntu
```
Чтобы посмотреть образы введите команду:
```bash
docker images
```
Чтобы удалить образ введите команду:
```bash
docker rmi image_id
```
Где `image_id` - это айди вашего образа.

Чтобы зайти в созданный образ:
```bash
docker run -it static-jinja-plus:ubu
```
Здесь используется виртуальное окружение, для запуска скриптов необходимо ввести команду
```bash
source vevn/bin/activate
```

### Сборка на базе Python-Slim
В директории `dock_file_slim` лежат файлы `Dockerfile` и `requirements` .
Для сборки образа последней версии StaticJinjaPlus на базе **python3.12-slim** введите в терминале:
```bash
docker build -t static-jinja-plus:slim ./dock_file_slim
```
В файле `requirement` указана последняя версия StaticJinjaPlus . 
Если вам нужна определенная версия **StaticJinjaPlus**, то укажите это в файле `requirements`. Например:
```requirements
staticjinjaplus == 2.0.0
```
Если нужна определенная версия **Python**, можно использовать аргумент  `PYTHON_VERSION`, например:
```bash
docker build --build-arg PYTHON_VERSION=3.10-slim -t static-jinja-plus:slim ./dock_file_slim
```

Чтобы посмотреть образы введите команду:
```bash
docker images
```
Чтобы удалить образ введите команду:
```bash
docker rmi image_id
```
Где `image_id` - это айди вашего образа.

Чтобы зайти в созданный образ:
```bash
docker run -it static-jinja-plus:slim bash
```

### Цель проекта

Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).


