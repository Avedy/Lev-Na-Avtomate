1) Webservak

1. Качаем nginx
2. Меняем в /etc/php-fpm.d/www.conf user и group на nginx
3. Там же меняем listen_allowed clients на 127.0.0.1:9000
4. Запускаем php-fpm service
5. Добавляем новый location в /etc/nginx/nginx.conf с index index.php и удаляем ::80
6. Создаем файлик index.php: nano /usr/share/nginx/html/index.php
7. Отключаем SeLinux 
8. Запускаем Nginx 
9. Первый пацанчик готов.

2) PGbratok
1. Качаем PostgreSQL
2. Ставим listen_addresses = '8' в nano /var/lib/pgsql/14/data/postgresql.conf
3. В nano /var/lib/pgsql/14/data/pg_hba.conf добавляем строку ip-шника сервака
4. Запускаем PostgreSQL 
5. Качаем и распаковываем БД файл в БДшку нашу 
6. Ставим пароль на БДшку
7. Отключаем SeLinux
8. Рестартим все системы в PG и Web, чтобы наверняка и видим вот это вот: