# Django fullstack example
This is an example to show how to integrate js-frontend. The key point is created a frontend app for django. And setup frontend related settings.  
Another key point is using `npm run build`, change `dist` to `templates` and django can find it to complete integration.

**Note**
Example in `vue.config.js`  

```js
module.exports = {
  outputDir: 'templates',
  assetsDir: "static",
}
```
# Performace test
uvicorn fullstack.asgi:application --workers 1 --log-level critical
uvicorn fullstack.asgi:application --workers 2 --log-level critical
gunicorn fullstack.asgi:application -w 2 -k uvicorn.workers.UvicornWorker

wrk -c 100 -d 30s -R 100 -L http://localhost:8000