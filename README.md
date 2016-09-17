Ansible Role: Gogs Git Server
==============================

Provisions [Gogs - Go Git Service](https://gogs.io/) - a painless self-hosted Git service

Examples
--------

### Gogs with SMTP Email transport and MySQL backend
```yaml
- role: gronke.gogs
  gogs_secret_key: '{{gogs.secret_key}}'
  gogs_config:
    app_name: 'Example Gogs Server'
    server:
      root_url: 'https://git.example.com/'
    database:
      host: "{{mysql_host}}"
      user: "{{mysql_user}}"
      name: "{{mysql_db_name}}"
      passwd: "{{mysql_password}}"
    mail:
    	from: "no-reply@example.com"
  gogs_smtp:
  	host: "smtp.example.com"
  	port: "587"
  	user: "service+gogs@example.com"
  	password: "correct horse battery staple"
```

Gogs listens on TCP port 3000 by default.