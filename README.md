# zabbix
## Projeto Cloud Treinamentos 
Criação de um SaaS para fornecer seriço de Monitoramento da Infra das Empresas

Primeiro Banco
imagem mysql-server(mysql)
    Variaveis
        MYSQL_DATABASE="zabbix"
        MYSQL_USER="zabbix"
        MYSQL_PASSWORD="zabbiz0123456"
        MYSQL_ROOT_PASSWORD="zabbix0123456"
        PORT 3306:3306

Segundo zabbix-java-gateway (Plugins Java Gateway)
imagem zabbix/zabbix-java-gateway

Terceiro zabbix-server-mysql
imagem zabbix/zabbix-server-mysql
    Variaveis
        DB_SERVER_HOST="mysql-server" (endPoint RDS)
        MYSQL_DATABASE="zabbix"
        MYSQL_USER="zabbix"  
        MYSQL_PASSWORD="zabbiz0123456"
        MYSQL_ROOT_PASSWORD="zabbix0123456"
        ZBX_JAVAGATEWAY="zabbix-java-gateway"
        PORTAS: 10051:10051

Quarto zabbix-web-mginx-mysql (Front)
imagem zabbix/zabbix-web-nginx-mysql
    Variaveis
        DB_SERVER_HOST="mysql-server" (endPoint RDS)
        MYSQL_DATABASE="zabbix"
        MYSQL_USER="zabbix"  
        MYSQL_PASSWORD="zabbiz0123456"
        MYSQL_ROOT_PASSWORD="zabbix0123456"
        PORTAS: 80:8080
        
Quinto zabbix_egent (Agente Zabbix)
imagem zabbix/zabbix_agent2
    Variaveis
        ZBX_HOSNAME="Zabbix Server"
        ZBX_SEVER_HOST="zabbix-server"
        PORT 10050:10050

Sexto Grafana
Imagem grafana/grafana

