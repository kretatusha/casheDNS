# casheDNS
Сервер прослушивает 53 порт. При первом запуске кэш пустой. Сервер получает от клиента рекурсивный запрос и выполняет разрешение запроса. Получив ответ, сервер разбирает пакет ответа, извлекает из него ВСЮ полезную информацию, т. е. все ресурсные записи, а не только то, о чем спрашивал клиент. Полученная информация сохраняется в кэше сервера.

Сервер регулярно просматривает кэш и удаляет просроченные записи, используя поле TTL.
Сервер не должен терять работоспособность, если старший сервер почему-то не ответил на запрос.
Сервер после получения сигнала о завершении работы сериализует данные из кэша и сохраняет их на диск.
При повторных запусках сервер считывает данные с диска и удаляет просроченные записи, инициализирует таким образом свой кэш.
Сервер умеет обрабатывать записи типов A, NS
Пример запуска в cmd: python server.py
Чтобы остановить процесс, в терминале Ctrl + C.
