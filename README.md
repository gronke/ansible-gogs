Ansible Role: Gogs Git Server
==============================

Provisions [Gogs - Go Git Service](https://gogs.io/) - a painless self-hosted Git service

Examples
--------

### Gogs with SMTP Email transport and MySQL backend
```yaml
- role: gronke.gogs
  gogs_secret_key: 'my-secret-key'
  gogs_config:
    app_name: 'Example Gogs Server'
    server:
      root_url: 'https://git.example.com/'
    database:
      host: "127.0.0.1"
      user: "root"
      passwd: ""
      name: "gogs_database_name"
    mail:
      from: "no-reply@example.com"
  gogs_smtp:
    host: "smtp.example.com"
    port: "587"
    user: "service+gogs@example.com"
    password: "correct horse battery staple"
```

Gogs listens on TCP port 3000 by default.
