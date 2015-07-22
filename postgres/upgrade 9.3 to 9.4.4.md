Solve problem on postgresql.
To day, I upgrade posgresql 9.3 to 9.4 on ubuntu. Because 9.3 unsupported JSONB datatype, i can jsonb for project Nodejs.

Here, I'm upgrade to postgres 9.4 successfully and I can't make postgres back 9.3 for tutorial. I hope you do it, and you can do it.
First of all, check version current postgres.

`$ whoami` 
* `postgres`

`$ psql`
* `version 9.3`

And check services postgres on system

`$ pg_lsclusters`

Continue, installation postgres 9.4

http://www.postgresql.org/download/linux/ubuntu/

Add repository for system.

Example: Trusty (14.04)

Create the file /etc/apt/sources.list.d/pgdg.list, and add a line for the repository.

`$ vim /etc/apt/sources.list.d/pgdg.list`
![vim](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot2.png)
Import the repository signing key, and update the package lists

`$ wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | \
  sudo apt-key add -`

`$ sudo apt-get update`

`$ sudo apt-get install postgresql-9.4`

Now, check status postgres 9.4 install success or error

Following command line obove for check postgres services `pg_lsclusters`
![pg_clusters](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot4.png)
![psql](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot3.png)
See, two version postgres is 9.3 and 9.4. But 9.4 is not running or system not used.
You can stop 9.3 and running 9.4 only.
![ps_dropcluster](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot5.png)

`$ sudo pg_dropcluster --stop 9.3 main`

Command: `$ ps_lsclusters`
![ps_lsclusters](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot6.png)
Ok, You trying connecting server posgres using pgadmin 3.

Critical, you know. Default postgres port is 5432 but it changed to 5433 after upgrade 9.4, it importion for you using connecting server. 

![ps_isready](https://raw.githubusercontent.com/flashjs/Docs/master/images/snapshot7.png)




