# laradock setup cheatsheet

http://laradock.io/  
docker package for laraval 

## Step
1. ```git clone https://github.com/LaraDock/laradock.git```
2. ```cd laradock/   ```
3. ```cp env-example .env```
4. edit .env  
   ```
   # Something you can customize
   APP_CODE_PATH_HOST=../my-laraval-app/
   COMPOSE_PROJECT_NAME=my-laraval-app
   NGINX_HOST_HTTP_PORT=8081
   ```
5. ```docker-compose up -d nginx ``` you can add mysql and other components behind.
6. Enter the container
   ```docker-compose exec --user=laradock workspace bash ```
7. Create laraval app in the container
   ``` composer create-project laravel/laravel . ```
8. edit .env of my-laraval-app
   ```  
      DB_HOST=mysql
      REDIS_HOST=redis
   ```
9. http://localhost:8081/ you should see the laraval welcome page (sometime try ```docker-compose down``` the Step 5) 
