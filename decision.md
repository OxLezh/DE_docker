В качестве основы берём образ continuumio/miniconda3:latest:
```bash
FROM continuumio/miniconda3:latest
```
Добавляем и делаем рабочей папкой /app:
```bash
WORKDIR /app
```
Копируем файл 1.sh внутрь контейнера:
```bash
COPY 1.sh /app/
```
Выдаем права на исполнение:
```bash
RUN chmod +x /app/1.sh
```
Запускаем установку пакетов python mlflow boto3 pymysql:
```bash
RUN conda install -y mlflow boto3 pymysql
```
Запускаем на вывод файл 1.sh:
```bash
CMD ["/app/1.sh"]
```
Собираем через docker build контейнера с тегом netology-ml:netology-ml:
```bash
docker build . -t netology-ml:netology-ml --no-cache --progress=plain 2>&1 | tee build.log
```
