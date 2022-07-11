# Getting

clone this repo

This is heavily based on the tutorial from: https://www.cirruslabs.io/blog1/modernized-technology/how-to-dockerize-an-web-application

# Building an image
`docker build -t myfirstwebapp .`

# Running an image created locally
`docker run -i -t -d -p 8080:8080 myfirstwebapp`

# Pushing an image to docker hub

```
docker push <your-user-name>/myfirstwebapp
```

# Running an image pushed to dockerhub

```
docker pull <your-user-name>/myfirstwebapp  # <--- gets the image onto your local machine
docker run -i -t -d -p 8080:8080 <your-user-name>/myfirstwebapp # <--- runs the remote image
```

# Accessing
http://localhost:8080/greeting

http://localhost:8080/greeting?name=test_name
produces the result:

```
{
"id": 1,
"content": "Hello, john!"
}
```

