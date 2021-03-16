**Running nginx and php in two separate container**  


`docker pull nginx`  
`docker pull php:fpm`  


`docker run --name fpm -d -v $(pwd)/index.php:/var/www/html/index.php`

`docker run --name web -d -p 8080:80 -v $(pwd)/default.conf:/etc/nginx/conf.d/default.conf -v $(pwd)/index.php:/var/www/html/index.php nginx`  

`docker network create my-net`  
`docker network connect my-net fpm`  
`docker network connect my-net web`    
