for latest mysql, change image with [mysql/mysql-server:latest]
         
     version: '3.8'
     services:
      db:
        image: mysql/mysql-server:latest
        container_name: mysql_latest
        environment:
          MYSQL_ROOT_PASSWORD: sap123ok
          MYSQL_DATABASE: test
          MYSQL_USER: hakim
          MYSQL_PASSWORD: sap123ok
        ports:
          - "3307:3306"
        networks:
          - mynetwork
    
    networks:
      mynetwork:
        driver: bridge

error message [Authentication plugin 'caching_sha2_password' cannot be loaded] 

		+ solution 
  
      + docker exec -it 3f sh
      + mysql -u root -psap123ok
      + ALTER USER 'hakim'@'%%' IDENTIFIED WITH mysql_native_password BY 'sap123ok';
      + restart docker container [docker restart 3f]
		
