# Troubleshooting

We collect the most common troubleshooting of using PostgreSQL for your reference:

> Many troubleshooting is closely related to the Server, if you can confirm troubleshooting is related to Cloud Platform, please refer to [Cloud Platform Documentation](https://support.websoft9.com/docs/faq/tech-instance.html)


#### Database service could not be started?

Insufficient disk space, insufficient memory, and configuration file errors can make database service could not be started

It is recommended to first check through the command.

```shell
# restart postgresql service
systemctl restart postgresql
systemctl status postgresql
journalctl -u postgresql

# view disk space
df -lh

# view memory rate
free -lh
```

#### The error "cannot be run as root Failure, exiting" when running the command `psql`?

For the security, the user **postgres** has been created in the process of installation, if you want to use the customer tool (e.g psql, pg_upgrade) on your PostgreSQL server, you should change the user first

```
sudo -i -u postgres
```