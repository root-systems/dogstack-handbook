# How to setup a Postgres database

## macOS

Use [Postgres.app](http://postgresapp.com/)

TODO documentation from a macOS user.

## Linux

(Based on ["How to set up Postgres database for local Rails project?"](https://stackoverflow.com/questions/19953653/how-to-set-up-postgres-database-for-local-rails-project#20305467))

1. Install postgresql and admin tools through the package manager

```shell
sudo apt-get install postgresql libpq-dev pgadmin3
```

2. Login to postgresql prompt as the postgres user

```shell
sudo su postgres -c psql 
```

3. Create a postgresql user for your project

```shell
create user username with password 'password';
```

4. Setup your postgres user with the same name and password as your normal user and make them a postgres superuser

```shell
alter user username superuser; 
```

5. Create the development and test databases

```shell
create database projectname_development;
create database projectname_test; 
```

6. Give permissions to the user on the databases

```shell
grant all privileges on database projectname_development to username;
grant all privileges on database projectname_test to username; 
```

To end the postgresql session type `\q`

Update password for the user

```shell
alter user username with password ‘new password’;
```

## Running seeds and migrations

With our [example app](./how-to-create-app), we can run our migrations and seeds.

### Migrations

Run latest migrations:

```shell
npm run migrate:latest
```

Rollback migrations:

```shell
npm run migrate:rollback
```

### Seeds

Seed database:

```shell
npm run seed
```
