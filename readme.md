На клиенте генерим ключи 

ssh-keygen -t rsa      

считываем открытый ключ 

cat ~/.ssh/id_rsa.pub

Заходим на сервак

Открываем файл

nano cat ~/.ssh/authorized_keys

вставляем в него новый открытый ключ с клиетской машины в конец 

ctrl+O сохраняяем

перезагружаем ssh сервер 

service ssh restart 
