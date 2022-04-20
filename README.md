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