# MySQL

## Table of Contents

- [Install](#install)
- [Initial Setup](#initial-setup)
- [Start Database](#start-database)
- [Connect to Root](#connect-to-root)
- [Create Database](#create-database)
- [Create User](#create-user)
- [Privilege](#privilege)
- [Drop](#drop)

---

## Install

```sh
sudo apt install mysql-server mysql-client mysql-common
```

---

## Initial Setup

```sh
sudo mysql_secure_installation
```

- **password validation**: `n`
- All the others: `y`

---

## Start Database

- Check services:

```sh
systemctl status mysql
```

- Start:

```sh
systemctl start mysql
```

- Stop:

```sh
systemctl stop mysql
```

- Restart:

```sh
systemctl restart mysql
```

---

## Connect to Root

User name and password in one line.

```sh
mysql -u root -p<password>
```

> [!IMPORTANT]
> No space between `-p` option and password.

---

## Create Database

```sql
CREATE DATABASE <db_name>;
```

- List Databases:

```sql
SHOW DATABASES;
```

- Show Current Database:

```sql
SELECT DATABASE();
```

---

## Create User

```sql
CREATE USER '<user_name>'@'localhost' IDENTIFIED BY '<password>';
```

- List Users:

```sql
SELECT user, host FROM mysql.user;
```

---

## Privilege

Grant every privilege on a specific DB:

```sql
GRANT ALL PRIVILEGES ON <db_name>.* TO '<user_name>'@'localhost';
```

Apply changes:

```sql
FLUSH PRIVILEGES;
```

## Root User's PW

After fresh install when there was no prompt to set root PW and now you can't
use MySQL.

Start MySQL with sudo:

```sh
sudo mysql
```

At the `mysql>` prompt, change root's password and apply changes:

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '<new_password>';
FLUSH PRIVILEGES;
```

---

## Drop

- Drop Database:

```sql
drop database <db_name>;
```

- Drop User:

```sql
drop user '<user_name>'@'localhost';
```

---

## MySQL Workbench

Install the `.deb` file from [MySQL downloads](https://dev.mysql.com/downloads/workbench/).

- Select OS
- Select version
- Install `mysql-workbench-community` version (one with smaller file size).
