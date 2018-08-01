# ldap-docker

Run OpenLDAP, phpLDAPadmin with docker-compose

1. Install docker and docker-compose
2. Install certbot:

```
apt-get update
apt-get install software-properties-common
add-apt-repository ppa:certbot/certbot
apt-get update
apt-get install certbot 
certbot certonly -d ldap.example.com
```

3. Run:

```
docker-compose up -d
```

4. Go to `https://ldap.example.com`:

```
LOGIN: cn=admin, dc=example, dc=com
PASS: admin_password
```

More info: https://www.techrepublic.com/article/how-to-populate-an-ldap-server-with-users-and-groups-via-phpldapadmin/
