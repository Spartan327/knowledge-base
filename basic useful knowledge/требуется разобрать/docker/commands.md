`docker login url_registri -u user_name -p password`

`docker images` образы контейнеров (-q вывести только id)
docker search имя образа
docker pull имя образа скачать

docker ps показать запущенные контейнеры ( -a + остановленные)
docker run -it запустить контейнер интерактивно с выделение отдельного терминала (-p перенаправление портов)
`docker run -d` запустить как демона (работа в фоне)
`docker run --name` присвоить контенеру имя  ОБРАЗ из которого будет запуск
доп параметры `--rm` удалить контейнер после остановки
`-p` проброс порта наша машина:порт в контейнере
`-e TZ=Europe/Moscow` установка переменной
`-v` проброс папки в контейнер
`-v` путь хостовой машины, наша машина:абсолютный путь в контенере (или использовать docker volume)

`docker build -t` имя образа ИМЯ_ОБРАЗА . путь от куда собирать (можно указать . из текущец директории)
`docker exec -it` выполнить на контейнере
`docker commit` id_контейнера

`docker rm $(sudo docker ps -qa)` удалить все контейнеры
`sudo docker rmi $(sudo docker images -q)`

`docker inspect`  узнаем идентификатор
процесса контейнера в операционной системе хоста

`docker port` узнать порт, который был выделен контейнеру,
можно командой 

в cent os необходимо выдать разрешение на директорию при монитровании в контейнер
chcon -R -t container_file_t /root/wwwbackup


Вот быстрый однострочник, который отображает статистику всех ваших работающих контейнеров
`docker ps -q | xargs  docker stats --no-stream`