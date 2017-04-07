# Nginx

[![Build Status](https://travis-ci.org/rvalente/ansible-role-nginx.svg?branch=master)](https://travis-ci.org/rvalente/ansible-role-nginx)

Install and configure Nginx Web Server.

Right now, this sets up an Nginx server that is not listening anywhere. The idea behind this is that you setup/secure nginx for use, then a role that will leverage nginx will install the vhost and restart nginx using this handler.

## Requirements

No additional requirements.

## Role Variables

Gzip and SSL are default enabled, this configures SSL to have sane-secure defaults.

### Shared

```
nginx_gzip_enabled: true
nginx_ssl_enabled: true
nginx_dhparam_keysize: 4096
dns_servers: []
```

`dns_servers` defaults to google public dns, these are used for SSL

### Debian

```
nginx_user: www-data
nginx_worker_processes: auto
nginx_error_log: /var/log/nginx/error.log
nginx_error_log_level: crit
nginx_pid: /run/nginx.pid
nginx_worker_connections: "1024"
nginx_access_log: /var/log/nginx/access.log
nginx_access_log_format: combined
```

### RedHat

```
nginx_user: nginx
nginx_worker_processes: auto
nginx_error_log: /var/log/nginx/error.log
nginx_error_log_level: crit
nginx_pid: /run/nginx.pid
nginx_worker_connections: "1024"
nginx_access_log: /var/log/nginx/access.log
nginx_access_log_format: combined
```

## Dependencies

- rvalente.epel

## Example Playbook

    - hosts: servers
      roles:
         - { role: rvalente.nginx }

## Testing

Running tests locally:

```
wget -O ${PWD}/tests/test.sh https://gist.githubusercontent.com/geerlingguy/73ef1e5ee45d8694570f334be385e181/raw/
chmod +x ${PWD}/tests/test.sh
```

## License

See `LICENSE`

## Author Information

Ronald Valente
