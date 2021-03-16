**Running nginx and php in two separate container**  


`docker pull nginx`  
`docker pull php:fpm`  

`docker network create my-net`    
`touch default.conf`  

    docker run -d -p 8080:80 -v $(pwd)/default.conf:/etc/nginx/conf.d/default.conf nginx  

    docker run -d -p 9000 php:fpm
