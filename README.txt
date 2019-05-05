# Exercise-3
Exercise 3: Linux problem solving

Troubleshooting Redis server issue

Below are the troubleshooting steps followed.

1) SSH to the Linux server
2) Tried starting the redis server by sudo systmctl start redis
3) It gave me an error "Job for redis-server.service failed because the control process exited with error code. See "systemctl status redis-server.sevice" and " Journalctl-xe"
4) checked the redis.conf file about the configuration to find if all conf is set right, din't notice anything fishy.
5) Tried executing the journalctl-xe to see why the redis server is failing to start and noticed the logfile /var/log/redis-server.log throwing an error.
6) Tried accessing the logfile path and was suprised to see the file doesnt exist, and found the redis.server.log was in a different location /var/log/redis/redis-server.log.
7) Proceeded forward to update the redis.conf file on the logfile path from /var/log/redis-server.log to /var/log/redis/redis-server.log
8) post updating the conf file started the redis server and found the server started.
9) Checked the status of the redis and made sure the redis is running.
10) Last but not least tried a redis-cli ping and was relieved to see PONG.
