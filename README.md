# meganode
MySQL backed Minima node with MEG as a multi-container docker image 

Public MDS is also enabled by default - can be accessed at https://127.0.0.1:9003/public/

### Installation

You must have docker installed.

Clone this repo

```
git clone https://github.com/minima-global/meganode.git
```

There are certain values in the **docker-compose.yml** file you may want to edit

- The MDS password for Minima
- The admin password for MEG
- The Minima / MEG / MySQL ports and if they should be exposed
- The initial peers to connect to can be set up later or directly from the params passed to Minima

You can of course change _any_ parameters you want - just add / remove them as environment variables 

Once you have set those up run

```
docker-compose up -d
```

And thats it.. you will now have a MegaMMR Minima node that is backed by a MySQL database

MEG will be running - and all the plumbing is set up auto-magically so that MEG and Minima can talk to each other

The Minima data folder is mappedf to the local **data** folder 

A daily backup of your MegaMMR and MySQL database is put in **backups** 

Startup takes about ~20 seconds.. before you can login to MDS or use MEG

This is because Minima waits for the MySQL DB to initialise fully - then MEG waits for Minima.. 

### Historical Data

This setup will record all data / TxPoW from the moment you start it

If you wish to load ALL old data you will need to :

- Copy a ..raw.dat backup into the data folder (you can find one on [spartacusrex.com](https://spartacusrex.com))
- Open Terminal on MDS
- run 

```
mysql action:reset file:theRawDatfile.raw.dat
```

You will now have a complete system with ALL data.
