# MSSQL

## Pull Image
```bash
$ docker pull microsoft/mssql-server-linux:2017-latest
```

## Run Container Image
```bash
$ docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=P@ssw0rd' \
   -p 1401:1433 --name sql1 \
   -d microsoft/mssql-server-linux:2017-latest
```

## Show Container
```bash
$ docker ps -a
```

## Connect Database
```bash
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'P@ssw0rd'
```

## Create Database
```bash
1> create database TestDB
2> select name from sys.Databases
3> GO
```

## Insert Data
```bash
1> use TestDB
2> create table Inventory (id int, name nvarchar(50), quantity int)
3> insert into Inventory values (1, 'banana', 150)
4> insert into Inventory values (2, 'orange', 154)
4> GO
```

## Select Data
```bash
1> select * from Inventory where quantity > 152
2> go
```

## Exit SQLCMD
```bash
1> quit
```

## Connect with MSSQL-CLI
```bash
mssql-cli -S 10.100.100.244 -U SA -W 'P@ssw0rd'
```

## Credit
https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker