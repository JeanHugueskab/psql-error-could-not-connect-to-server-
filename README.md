# psql-error-could-not-connect-to-server-

Cheatsheet in case of this following error :

    "psql: error: could not connect to server: could not connect to server: No such file or directory
	    Is the server running locally and accepting
	    connections on Unix domain socket "/tmp/.s.PGSQL.5432"?" 

      rm -rf /usr/local/var/postgres  # in case this is not your first try
      mkdir /usr/local/var/postgres
      chmod 0700 /usr/local/var/postgres

        Then run initdb and it will respect the permissions of the data directory.

          initdb -D /usr/local/var/postgres
           create a test db named after your user:

             createdb `whoami`
  
             Login to test:
                 psql
