# pgRouting - Routing Functionalities on PostgreSQL

## INTRODUCTION

This library contains following features:

* Dijkstra algorithm - Shortest path algorithm, which named in honor
  of Prof. Dr. Edsger Wybe Dijkstra who has invented it
* A-star (A*) algorithm - Shortest path algorithm using heuristical 
  function
* Driving distance - area person can cover in certain time from start
  point using road network
* TSP - Travelling Salesman Problem solution with default mazimum of
  40 points
* Shooting star (Shooting*) algorithm - Shortest path algorithm for
  real road networks with turn restrictions, traffic lights and one
  way streets. 

## REQUIREMENT

See online documentation:
http://www.pgrouting.org/docs/1.x/install.html


## INSTALLATION

See online documentation:
http://www.pgrouting.org/docs/1.x/install.html


## COMPILATION

For MinGW on Windows

    mkdir build
    cd build
	cmake -G"MSYS Makefiles" -DWITH_TSP=ON -DWITH_DD=ON ..
	make
	make install

For Linux
	
    mkdir build
    cd build
	cmake -DWITH_TSP=ON -DWITH_DD=ON ..
	make
	sudo make install

Build with documentation (requires Sphinx)

	cmake -DWITH_DOC=ON -DWITH_TSP=ON -DWITH_DD=ON ..

Postgresql 9.1+

	createdb mydatabase
	psql mydatabase -c "create extension postgis"
	psql mydatabase -c "create extension pgrouting"

For older versions of postgresql

	createdb -T template1 template_postgis
	psql template_postgis -c "create language plpgsql"
	psql template_postgis -f /usr/share/postgresql/8.3/contrib/postgis-1.5/postgis.sql
	psql template_postgis -f /usr/share/postgresql/8.3/contrib/postgis-1.5/spatial_ref_sys.sql
	psql template_postgis -f /usr/share/postgresql/8.3/contrib/postgis_comments.sql

	createdb -T template_postgis template_pgrouting
	psql template_pgrouting -f /usr/share/pgrouting/pgrouting--1.0.7.sql

	createdb -T template_pgrouting mydatabase


## USAGE

See online documentation:
http://www.pgrouting.org/docs/1.x/index.html


## LICENCE

Most features are available under GPL.
Some Boost extensions are available under Boost license (see LICENSE_1_0.txt)
Some code contributed by iMaptools.com is available under MIT-X license.