# Maria DB Replication
Database replication is the process of creating and maintaining multiple copies of a database, either on the same server or on different servers, to ensure that the data is consistent and available to users at all times.

In a replicated database, changes made to the original database are automatically propagated to the replicated copies. This allows multiple users to access and work with the same data simultaneously, even if they are located in different locations.

Replication can be done in a variety of ways, depending on the specific needs of the organization. Some common types of replication include:

## Master-Master Replication

In this type of replication, two or more database servers act as masters, and changes can be made to any of the servers. Changes made to one master are automatically replicated to the other masters so that all databases are kept in sync.

### Pros and Cons

#### Pros
- Application can read and write from both Master Database.
- Simple configuration to set up master-master database replication
- Simple, easy and quick failover

#### Cons
- Loosely consistent
- If the application has a high load, then the replication between the master-master database will drag the read and write of the database slower.

## Master-Slave Replication

In this type of replication, one database server acts as the master and all changes to the database are made on the master. The changes are then replicated to one or more slave servers, which have a copy of the data that is kept in sync with the master.

### Pros and Cons

#### Pros
- Retrieve the data from the master without affecting the performance of the application.
- Back up the entire database from the master to the slave database without having any impact on the master.
- Slaves can be taken offline and can be synced back to the master without having offline for some time.

#### Cons
- If the master database has a huge gap in the data that didn't send to the slave, the replication between master and slave will be cut off.
- If the master is down, the slave should be promoted to be the master manually. There is no automatic failover between master and slave.
- In master-slave design, the writer should go to the master and not the slave. Or not the master-slave replication will be down.

## Multi-Master Replication

This type of replication allows changes to be made to any of the servers in the cluster, and the changes are propagated to all other servers in the cluster. This is commonly used in distributed databases where there is no centralized master.

### Pros and Cons

#### Pros:

- **Data Consolidation:** Multi-source replication allows you to consolidate data from different sources into a single replica, making it easier to analyze and report on data from multiple databases in one place.

- **Reduced Infrastructure Costs:** Instead of maintaining a separate replica for each master, you can use a single replica to replicate data from multiple masters, potentially reducing hardware and maintenance costs.

- **Simplified Management:** Managing a single replica for multiple sources can be more streamlined than managing separate replicas for each source.

- **Resource Efficiency:** With proper resource allocation, a single replica can handle the replication from multiple sources, making more efficient use of system resources.

#### Cons:

- **Complexity:** Multi-source replication can be more complex to set up and maintain than traditional replication setups, as you have to manage multiple replication channels, configurations, and potential conflicts.

- **Increased Risk of Conflicts:** Replicating data from multiple sources into a single replica increases the risk of conflicts or data inconsistencies, especially if the sources have overlapping data.

- **Performance Impact:** Depending on the number of sources and the volume of changes, replicating data from multiple sources to a single replica may impact the performance of the replica server.

- **Potential Latency:** Replicating data from multiple sources could introduce latency, especially if the sources are geographically dispersed or have varying update frequencies.

- **Dependency on Multiple Masters:** If one of the master servers fails or experiences issues, it can affect the data replication process from all sources to the replica.

- **Limited to Same DBMS:** Multi-source replication typically requires all sources and the replica to use the same database management system (e.g., MariaDB to MariaDB), limiting flexibility if you need to replicate data across different types of databases.

- **Potential Resource Contentions:** If multiple sources are actively replicating to the same replica, there might be resource contentions that affect the overall performance of the replica server.
