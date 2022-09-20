# Database-Replication
This is guide for Database Replication in Maria Database, that can be done with the steps and FAQ

For the Maria Database there is two type of replication can be done one is Master-Master replication also known as Galera Cluster and another is Master-Slave Replication.

Master-Master Replication
Master-Master Replication or Galera Cluster is a synchronus multi-master database cluster, based on synchronus replication and MySQL and InnoDB. When the Master-Master replication have apply in the database, any node can perform both write and read in the replication cluster.

Pros and Cons
Pros
- Application can read and write from both Master Database.
- Simple configuration in order to setup master-master database replication
- Simple, easy and quick failover

Cons
- Loosely consistent
- If the application having high load, then the replication between master-master database will drag the read and write of database to slower.

Master-Slave Replication
Master-Slave Replication involves in caching data from the master database to slave database. This replication process will replicate the copies from the parents database to multiple server simultaneously.

Pros and Cons
Pros
- Retrieve the data from the master without affecting the performance of the application.
- Backup entire database from the master to slave database without having any impact to the master.
- Slaves can be taken offline and can be sync back to the master without having offline for period time.

Cons
- If the master database have huge gap of the data that didnt send to slave, the replication between master and slave will be cut off.
- If the master is down, slave should be promoted to be the master manually. There is no automatic failover between master and slave.
- In master-slave design, the write should go to the master and not the slave. Or not the master-slave replication will be down.

