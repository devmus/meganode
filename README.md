# meganode
MySQL backed Minima node with MEG as a multi-container docker image 

### Installation

You must have docker installed.

Clone this repo

```
git clone https://github.com/minima-global/meganode.git
```

There are certain values in the **docker-compose.yml** file you will want to edit

- The MDS password for Minima
- The admin password for MEG
- Do you want to change the ports

Once you have set those up run

```
docker-compose up -d
```

And thats it.. you will now have a MegaMMR Minima node that is backed by a MySQL database

MEG will be running - and all the plumbing is set up auto-magically so that MEG and Minima can talk to each other

The Minima data folder is /data 

A daily backup of your MegaMMMR and MySQL database is put in backups 

### Historical Data

This setup will record all data / TxPoW from the moment you start it

If you wish to load ALL old data you will need to :

- Copy a ..raw.dat backup into the data folder

