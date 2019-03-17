### Requirements

- Postgresql 10
- zip

**ZIP **
```sh
sudo apt-get install zip
```

**Postgresql**

For Debian 9
```sh
sudo nano /etc/apt/sources.list.d/pgdg.list
# Add to file
deb http://apt.postgresql.org/pub/repos/apt/ stretch-pgdg main

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt update
sudo apt install postgresql-10
# Check version of php
sudo apt install php-pgsql
```

Install postgresql and enable this for php
```sh
sudo apt update
sudo apt install postgresql postgresql-contrib
sudo apt install php-pgsql
```

User and database creation
```sh
sudo -u postgres createuser test_user
sudo -u postgres createdb test_database
sudo -u postgres psql

# PSQL shell
alter user test_user with encrypted password '123';
grant all privileges on database test_database to test_user;
\q
```

**Access DB**
```sh
psql -h 127.0.0.1 -U test_user -d test_database
```

**Configure automatic backups**

Edit crontab
```sh
  sudo crontab -e
```
see use of crontab
https://crontab.guru/
