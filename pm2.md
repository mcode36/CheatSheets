# Simple start up

Assuming we have an app hello.js

- To start
$ pm2 start hello.js

- To list all managed processes
$ pm2 list

- To stop
$ pm2 stop hello

- To remove app from list
$ pm2 delete hello

- To start app with system env variable setup:
$ pm2 ecosystem
$ vi ecosystem.config.js
(stop existing processes if still running)
$ pm2 start ecosystem.config.js
or
$ pm2 [start|restart|stop|delete] ecosystem.config.js

# Official documentation page
https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/