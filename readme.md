На клиенте генерим ключи 

ssh-keygen -t rsa      

считываем открытый ключ 

cat ~/.ssh/id_rsa.pub

Заходим на сервак

Открываем файл

nano cat ~/.ssh/authorized_keys

подключаемся 

вставляем в него новый открытый ключ с клиетской машины в конец 

ctrl+O сохраняяем

перезагружаем ssh сервер 

service ssh restart 

подключаемся к серверу 

ssh user@host // пример ssh root@11.11.11.11 -p 22 (порт)


Отключение проверки пароля

nano /etc/ssh/sshd_config

PasswordAuthentication no
