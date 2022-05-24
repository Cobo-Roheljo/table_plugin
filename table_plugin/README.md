1. Devi aprire il container di apache di mysql

    Per avviare il container apache esegui questo comando sul cmd: "docker run -d -p 8090:80 --name my-apache-php-app --rm  -v /home/informatica/table_plugin:/var/www/html zener79/php:7.4-apache/home/informatica/table_plugin.

    Per avviare invece il container mysql esegui questo comando:
    "docker run --name my-mysql-server --rm -v /home/informatica/mysqldata:/var/lib/mysql -v /home/informatica/dump:/dump -e MYSQL_ROOT_PASSWORD=my-secret-pw -p 3306:3306 -d mysql:latest.

2. Scaricare il file create_employee.sql che contiene il codice per creare il database il quale va inserito nella cartella dump creata prima
    
    Caricare il file appena scaricato sul container MYSQL attraverso i seguenti comandi:
    docker exec -it my-mysql-server bash mysql -u root -p < /dump/create_employee.sql; 
    exit;

3. Collegati al browser tramite l'URL:
    
    localhost:8090/tabella.html per visualizzare il frontend
    localhost:8090/index.php per visualizzare il backend in formato json

4. Hai effettuato il collegamento

-- Funzioni --  
Puoi provare queste funzioni:

- aggiunta di un dipendente
- modifica di un dipendente
- eliminazione di un dipendente
- ricerca di un dipendente
- paginazione dinamica:
    - la pagina attuale 
    - la pagina precendete
    - la pagina successiva
    - la prima pagina 
    - ultima pagina