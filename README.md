# Database-Replication
This is guide for Database Replication in Maria Database, that can be done with the steps and FAQ

For the Maria Database there is two type of replication can be done one is Master-Master replication also known as Galera Cluster and another is Master-Slave Replication.

Master-Master Replication
Master-Master Replication or Galera Cluster is a synchronus multi-master database cluster, based on synchronus replication and MySQL and InnoDB. When the Master-Master replication have apply in the database, any node can perform both write and read in the replication cluster.

Master-Slave Replication
Master-Slave Replication involves in caching data from the master database to slave database. This replication process will replicate the copies from the parents database to multiple server simultaneously.
