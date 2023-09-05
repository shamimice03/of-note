### Prerequisite
- Attach `ElastiIP` on the target EC2 instance
- Create two DNS record on route53.
  - prometheus.kubecloud.net ------ A ------- `elastic-ip`
  - www.prometheus.kubecloud.net ------- A ------- `elastic-ip`
- For the sake of the configuration open all incoming traffic in the target instance security group
  
### Install `certbot` on `amazon linux 2`
```
sudo yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum install -y certbot
```

```
sudo certbot certonly --standalone -d prometheus.kubecloud.net  -d  www.prometheus.kubecloud.net
```

Following the promt:
```
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/prometheus.kubecloud.net/fullchain.pem   <----------------------
   Your key file has been saved at:
   /etc/letsencrypt/live/prometheus.kubecloud.net/privkey.pem     <----------------------
   Your certificate will expire on 2023-12-04. To obtain a new or
   tweaked version of this certificate in the future, simply run
   certbot again. To non-interactively renew *all* of your
   certificates, run "certbot renew"
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le
```

### Install nginx:
```
sudo yum install -y nginx
```

### Add following lines in `nginx.conf`

```
sudo vim sudo nano /etc/nginx/nginx.conf
```

#### Template
```bash
server {
    listen 80;
    server_name yourdomain.com www.yourdomain.com;
    location / {
        return 301 https://$host$request_uri;
    }
}

server {
    listen 443 ssl;
    server_name yourdomain.com www.yourdomain.com;

    ssl_certificate /etc/letsencrypt/live/yourdomain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/yourdomain.com/privkey.pem;

    location / {
        proxy_pass http://localhost:your-app-port;
    }
}
```

#### After applying
```bash
  server {
      listen 80;
      server_name prometheus.kubecloud.net www.prometheus.kubecloud.net;
      location / {
          return 301 https://$host$request_uri;
      }
  }
  
  server {
      listen 443 ssl;
      server_name prometheus.kubecloud.net www.prometheus.kubecloud.net;
  
      ssl_certificate /etc/letsencrypt/live/prometheus.kubecloud.net/fullchain.pem;
      ssl_certificate_key /etc/letsencrypt/live/prometheus.kubecloud.net/privkey.pem;
  
      location / {
          proxy_pass http://localhost:9090;
      }
  }
```

#### Restart 
```
sudo systemctl restart nginx
```

### Renew cert
Remember to renew your SSL certificate every 90 days if you’re using Let’s Encrypt. You can automate this process with a cron job:
```
echo "0 12 * * * /usr/bin/certbot renew --quiet" | sudo tee -a /etc/crontab > /dev/null
```

### Ref:
- https://saturncloud.io/blog/installing-ssl-certificates-on-aws-ec2-instances-without-cloudfront-or-elastic-load-balancing/
