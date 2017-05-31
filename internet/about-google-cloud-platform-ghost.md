## How to send Email by Ghost on Google Cloud Platform 

After [Install Ghost on GCP by one click](https://console.cloud.google.com/launcher/details/bitnami-launchpad/ghost) . I notice that it can't sent invite email to others by itself. So we use Mailgun to solve mail things. 

But the problem is, Google Cloud Platform doesn't allow SMTP traffic through default ports: 25, 465, 587. 

We have to change the port to 2525.

Edit `/opt/bitnami/apps/ghost/htdocs/config.js` ：

```json
  mail: {  
    transport: 'SMTP',
    options: {
      service: 'Mailgun',
      port: 2525,
      auth: {
        user: 'postmaster@your_domain', 
        pass: 'your_password'  
      }
    }
  },
```

Save it and restart the ghost and apache. Good!

```shell
$ /opt/bitnami/ctlscript.sh restart ghost
$ /opt/bitnami/ctlscript.sh restart apache
```

- - -

## 如何使在 Google Cloud Platform 上面的 Ghost 發 Email

使用 [Google Cloud Platform 一鍵安裝 Ghost](https://console.cloud.google.com/launcher/details/bitnami-launchpad/ghost) 上去了之後，發現他無法發出 Email 給共同編輯者，

查了一下發現需要使用 Mailgun 之類的協助，而且因為 Google Cloud Platform 不允許 SMTP 使用 ports 25, 465, 587 ，

所以我們更改為 port 2525 來使用，

修改 `/opt/bitnami/apps/ghost/htdocs/config.js` ：

```json
  mail: {  
    transport: 'SMTP',
    options: {
      service: 'Mailgun',
      port: 2525,
      auth: {
        user: 'postmaster@your_domain', 
        pass: 'your_password'  
      }
    }
  },
```

儲存之後重新開啟 Ghost 跟 Apache 即可。

```shell
$ /opt/bitnami/ctlscript.sh restart ghost
$ /opt/bitnami/ctlscript.sh restart apache
```