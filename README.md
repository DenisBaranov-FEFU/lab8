Запуск 


сd ~/wazuh-docker/single-node


docker compose up -d

Доступ 
https://IP-АДРЕС


Логин:Пароль 
admin:SecretPassword


По умолчанию логи nginx собираются в формате JSON в директории /var/log/nginx/access_json.log и error_json.log соответсвенно

В случае если есть необходимость сменить директорию, то необходимо отредактировать docker-compose.yml в "wazuh-docker/single-node", чтобы монтировалась нужная директория, нужно внести правки в ossec.conf в той же директории в раздел "<-- Nginx JSON logs -->", указав нужный путь, и по аналогии в wazuh_cluster по пути "wazuh-docker/single-node/сonfig/wazuh_cluster/wazuh_manager.conf". 

Стандартный набор правил не дает той глубины и приятного чувства победа, поэтому используются кастомные правила, которые монтируются в "/var/ossec/etc/rules/local_rules.yml" декодер используется json стандартный. Декодер "json" т.е. у него "name=json", буквально. 
