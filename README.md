# DCMPM-Docker-Caddy-MySQL-PHP-Mailhog
Simple configuration for the containerization of web project. 
It includes 4 containers and it can be useful for the development of a webapp.
- Caddy (web server)
- PHP
- MySQL 
- MailHog (receive fake email)

# Utilization
You can configure the Dockerfiles and Dockercompose with your needs.   
You can see incoming mails at http://localhost:8025/

# Supported architectures
AMD64 (x86_64) and aarch64(ARM64) are supported. If you need other architectures change the download link of mhsendmail inside PHP/Dockerfile.   
Note that MailHog is only available with AMD64, no problems in macOS thanks to Rosetta2 

# Known issues 
Of course since Caddy runs inside a container and not in your host machine you need to install in the host machine the certificate for HTTPS (see https://caddyserver.com/docs/running#usage)
