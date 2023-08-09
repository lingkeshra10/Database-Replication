# Maria DB Replication
Database replication is the process of creating and maintaining multiple copies of a database, either on the same server or on different servers, to ensure that the data is consistent and available to users at all times.

In a replicated database, changes made to the original database are automatically propagated to the replicated copies. This allows multiple users to access and work with the same data simultaneously, even if they are located in different locations.

Replication can be done in a variety of ways, depending on the specific needs of the organization. Some common types of replication include:


## Master-Master Replication

Master-Master Replication or Galera Cluster is a synchronous multi-master database cluster, based on synchronous replication and MySQL and InnoDB. When the Master-Master replication has applied in the database, any node can perform both write and read in the replication cluster.

### Pros and Cons

#### Pros
- Application can read and write from both Master Database.
- Simple configuration in order to set up master-master database replication
- Simple, easy and quick failover

#### Cons
- Loosely consistent
- If the application has a high load, then the replication between the master-master database will drag the read and write of the database slower.

## Master-Slave Replication

Master-Slave Replication involves caching data from the master database to the slave database. This replication process will replicate the copies from the parent database to multiple servers simultaneously.

### Pros and Cons

#### Pros
- Retrieve the data from the master without affecting the performance of the application.
- Back up the entire database from the master to the slave database without having any impact on the master.
- Slaves can be taken offline and can be synced back to the master without having offline for a period of time.

#### Cons
- If the master database has a huge gap in the data that didn't send to the slave, the replication between master and slave will be cut off.
- If the master is down, the slave should be promoted to be the master manually. There is no automatic failover between master and slave.
- In master-slave design, the writer should go to the master and not the slave. Or not the master-slave replication will be down.

