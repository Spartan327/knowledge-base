**netcat -- утилита, которую можно использовать для перадачи файлов большого размера по tcp протоколу**
для передачи файлов придется открыть порты

**передача файла**
`nc -lp 8888 -q 1 <` + `имя_файла` -- добавляем в nc файл для передачи его тому, кто подключиться к серверу по 8888 порту, после передачи nc закроется через 1 секунду

**прием файла**
`nc ip_server 8888 >` + `имя_файла`