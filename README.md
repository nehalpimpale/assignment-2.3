# assignment-2.3

Q. All components of Hadoop 1.x :

1.NameNode

• Contains the Hadoop FileSystem Tree and other metadata information about files and directories.
• Contains in-memory mapping of which blocks are stored in which datanode.

2.Secondary NameNode

• Performs house-keeping activities for NameNodes, like the periodic merging of namespace and edits.
• This is not a back up for a NameNode.

3.DataNode

• Stores actual data blocks of files in HDFS on its own local disk.
• Sends signals to the NameNode periodically (called as Heartbeat) to verify whether it is active.
• Sends block reporting to the NameNode on the cluster startup as well as periodically at every 10th Heartbeat.
• The DataNodes are the workhorses of a system.
• They perform all the block operations including periodic checksum. They receive instructions from the name node of
where to put the blocks and how to put them.

4.JobTracker (Not present in Hadoop 2.x)

• Controls the overall execution of the MapReduce jobs

5.TaskTracker (Not present in Hadoop 2.x)

• Runs individual MapReduce jobs on DataNodes
• Periodically communicates with the JobTracker to give updates and receive instructions
