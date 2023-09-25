Сборка через docker build контейнера с тегом netology-ml:netology-ml:
```bash
docker build . -t netology-ml:netology-ml --no-cache --progress=plain 2>&1 | tee build.log
```
