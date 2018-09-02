# ldap-docker

Run [OpenLDAP](https://www.openldap.org/) and [phpLDAPadmin](http://phpldapadmin.sourceforge.net/wiki/index.php/Main_Page) using `docker-compose`

1. Install `docker` and `docker-compose`

```
apt update && apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
apt update && apt install docker-ce
curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

2. Install `certbot`:

```
apt-get update
apt-get install software-properties-common
add-apt-repository ppa:certbot/certbot
apt-get update
apt-get install certbot 
certbot certonly -d ldap.example.com
```

3. Edit env file and run `docker-compose`:

```
cp .env_example .env
vim .env
...

docker-compose up -d
```

4. Go to `https://ldap.example.com`:

```
LOGIN: cn=admin, dc=example, dc=com
PASS: admin_password
```

How to use phpLDAPadmin: [here](https://www.techrepublic.com/article/how-to-populate-an-ldap-server-with-users-and-groups-via-phpldapadmin/)
