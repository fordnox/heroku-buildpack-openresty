# heroku-buildpack-openresty

## Manual deployment

You will need to create a Heroku account and install the Heroku CLI, eg. `brew install heroku`

```
git clone git@github.com:fordnox/heroku-buildpack-openresty.git
cd heroku-buildpack-openresty
heroku container:login
heroku create
heroku container:push web
heroku container:release web
heroku open
```

## Local deployment

Assuming docker is already installed

```
echo "127.0.0.1 openresty" >> /etc/hosts
export PORT=8080
docker build --tag openresty:1.0 .
docker run --publish 8000:8080 --detach --name openresty openresty:1.0
```
