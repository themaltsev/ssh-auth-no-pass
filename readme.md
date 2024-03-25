Если уже имеется ключ!!!!

заливаем сюда ~/.ssh/

Выставляем права на ключи

chmod 600 ~/.ssh/id_rsa   

chmod 644 ~/.ssh/id_rsa.pub

Если вы используете SSH-агент для управления своими ключами, убедитесь, что ваш ключ загружен в агент. Вы можете проверить агент, используя следующую команду:

ssh-add -l  

Если агент не запущен, вы можете запустить его с помощью команды:

eval "$(ssh-agent -s)"   

ssh user@host // пример ssh root@11.11.11.11 -p 22 (порт)


ЕСЛИ КЛЮЧА НЕТ!!!!!!

На клиенте генерим ключи 

ssh-keygen -t rsa   

считываем открытый ключ 

cat ~/.ssh/id_rsa.pub

Заходим на сервак

Открываем файл

nano cat ~/.ssh/authorized_keys

вставляем в него новый открытый ключ с клиетской машины в конец 

ctrl+O сохраняяем

ВТОРОЙ способ залить пароль на сервер
cat ~/.ssh/id_rsa.pub | ssh username@remote_host "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

перезагружаем ssh сервер 

service ssh restart 

подключаемся к серверу 

ssh user@host // пример ssh root@11.11.11.11 -p 22 (порт)


Отключение проверки пароля

nano /etc/ssh/sshd_config

PasswordAuthentication no

