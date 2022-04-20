## NGinx serving static files in different directories
![use_case_01](images/use_case_01.jpg)
```
events{}
http{
    include mime.types;
    server{
        listen 80;
        server_name localhost;
        root /usr/local/opt/nginx/html/site01;
    }
    server{
        listen 90;
        server_name localhost;
        root /usr/local/opt/nginx/html/site02;
    }
}
```

## NGinx serving static files trhough differents locations
![use_case_02](images/use_case_02.jpg)
```
events{}
http{
    include mime.types;
    server{
        listen 80;
        server_name localhost;
        #Prefix match
        location /site1 {
            alias /usr/local/opt/nginx/html/site01/;
        }
        #Prefix match
        location /site2 {
            alias /usr/local/opt/nginx/html/site02/;
        }
    }
}
```