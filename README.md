ShellDB is a fast and minimal document database.

Its scope is to store and retrieve data structures partial or completed. Inserted data can overwrite or append each other. During time the stored data structure is getting more complex.

To retrieve exactly the documents parts you want there are simple filters you can use. Details are at the corresponded documentation.

All operation are performed from the http REST API served from an embedded lighthttpd web server listening at port 7000 by default. This embedded lighthttpd do not conflict with any other web server you may have.

The database data files are compressed private Btrfs volumes. These volumes are pointing to regular files, created when you create a new database, and deleted when you drop it.

Why ShellDB is fast.

The data structures are stored inside the Btrfs volumes as common files and directories.  The directories are used to store the key names while the files are storing their values.
Except from the embedded web server, there is no other process running to slow down your server or to consume your server memory. Also it is almost impossible to corrupt a database because there are not any index files.

The insert,query,delete etc requests, are performed from very small and fast shell scripts, so that’s where ShellDB name is came from. For the time being only linux is supported.

To stop, start the embedded web server and mount your databases use

	systemctl (start|stop|status) shelldb

The install, uninstall procedure is dead simple

	git clone https://github.com/GeorgeBouras/ShellDB.git
	cd ShellDB
	./install --install
	./install -–remove
	./install --remove purge	( remove also the DBs )
	./install --version
	./install --help
	./install -–about
	./install -–license

That is all you need to know to have ShellDB started. So get the code, install it, read the short API documentation and have some fun with it.

<a href="https://github.com/GeorgeBouras/ShellDB/blob/master/documentation/01%20generic.txt">Generic</a>

<a href="https://github.com/GeorgeBouras/ShellDB/blob/master/documentation/02%20manage%20databases.txt">Manage databases</a>

<a href="https://github.com/GeorgeBouras/ShellDB/blob/master/documentation/03%20insert%2C%20update%2C%20delete%20data.txt">Insert, Update, Delete, Rename, Check data</a>

<a href="https://github.com/GeorgeBouras/ShellDB/blob/master/documentation/04%20query.txt">Reporting</a>

<a href="https://github.com/GeorgeBouras/ShellDB/blob/master/documentation/05%20local%20operations.txt">Local operations</a>

George Bouras
georgios.mpouras@gmail.com
