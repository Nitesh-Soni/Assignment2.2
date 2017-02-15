# Assignment2.2
1. HDFS

The file store in HDFS provides scalable, fault-tolerant storage at low cost.
- The HDFS software detects and compensates for hardware issues, including disk problems
and server failure.
- HDFS stores files across the collection of servers in a cluster.
- Files are decomposed into blocks and each block is written to more than one of the
servers.
- The replication provides both fault-tolerance and performance.
HDFS has been designed keeping in view of the following features:
- Very large files: Files that are megabytes, gigabytes, terabytes, or petabytes of size.
- Streaming data access: HDFS is built around the idea that data is written once but
read many times. A dataset is copied from source and then analysis is done on that
dataset over time.
- Commodity hardware: Hadoop does not require expensive, highly reliable hardware
as it is designed to run on clusters of commodity hardware.

One hard drive in 1990 could store 1,370 MB of data and had a transfer speed of 4.4 MB/s.
So full data could be read in five minutes.
- Now, with 1-terabyte drive transfer speed is around 100 MB/s.
- But it takes more than two and a half hours to read all the data off the disk.
- Although, the storage capacities of hard drives have increased, yet access speeds have not
kept up.
- If we had 100 drives, each holding one hundredth of the data, then working in parallel,
we could read the data in under two minutes.
- This is very much similar to distribution of work in any firm.

2. Hadoop Clusters

In a computer system, a cluster is a group of servers and other resources that act like a single system and enable high availability and,
in some cases, load balancing and parallel processing.
Data Storage has grown exponentially in the recent past, but data reading speed has not
improved radically.


Hadoop clusters are known for boosting the speed of data analysis applications. They also are highly scalable: If a cluster's processing power 
is overwhelmed by growing volumes of data, additional cluster nodes can be added to increase throughput.
Hadoop clusters also are highly resistant to failure because each piece of data is copied onto other cluster nodes, 
which ensures that the data is not lost if one node fails.

Since a cluster is a logical rather than a physical unit (it's not built into the hard disk itself), the size of a cluster can be varied. The maximum number of clusters on a hard disk depends on the size of a FAT table entry. 
Beginning with DOS 4.0, the FAT entries were 16 bits in length, allowing for a maximum of 65,536 clusters. Beginnning with the Windows 95 OSR2 service release, a 32-bit FAT entry is supported, allowing an entry to address enough clusters to support up to two terabytes of data (assuming the hard disk is that large!).

The tradeoff in cluster size is that even the smallest file (and even a directory itself) takes up the entire cluster. 
Thus, a 10-byte file will take up 2,048 bytes if that's the cluster size. 
In fact, many operating systems set the cluster size default at 4,096 or 8,192 bytes. 
Until the file allocation table support in Windows 95 OSR2, the largest size hard disk that could be supported in a single partition was 512 megabytes. 
Larger hard disks could be divided into up to four partitions, each with a FAT capable of supporting 512 megabytes of clusters.

As of early 2013, Facebook was recognized as having the largest Hadoop cluster in the world. Other prominent users include Google, Yahoo and IBM.

3. HDFS blocks

Hadoop distributed file system also stores the data in terms of blocks. However the block size in HDFS is very large. The default size of HDFS block is 64MB. The files are split into 64MB blocks and then stored into the hadoop filesystem. The hadoop application is responsible for distributing the data blocks across multiple nodes. 

The benefits with HDFS block are: 
- The blocks are of fixed size, so it is very easy to calculate the number of blocks that can be stored on a disk.
- HDFS block concept simplifies the storage of the datanodes. The datanodes doesn’t need to concern about the blocks metadata data like file permissions etc. 
The namenode maintains the metadata of all the blocks.
- If the size of the file is less than the HDFS block size, then the file does not occupy the complete block storage. 
- As the file is chunked into blocks, it is easy to store a file that is larger than the disk size as the data blocks are distributed and stored on multiple nodes in a hadoop cluster.
- Blocks are easy to replicate between the datanodes and thus provide fault tolerance and high availability. Hadoop framework replicates each block across multiple nodes (default replication factor is 3). 
In case of any node failure or block corruption, the same block can be read from another node.
