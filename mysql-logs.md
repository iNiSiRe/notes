# MySQL redo-, bin-, relay- logs

### Links
- https://dev.mysql.com/doc/refman/5.7/en/innodb-redo-log.html
- https://dev.mysql.com/doc/refman/5.7/en/innodb-redo-log-buffer.html
- https://dev.mysql.com/doc/refman/5.7/en/replica-logs-relaylog.html
- https://dev.mysql.com/doc/refman/5.7/en/binary-log.html

### Purpose
Redo Log - committed transactions, not changed data on disk
Binary Log - committed transactions that changed data on disk
Relay Log - ?

### InnoDB redo log:
Disk-based data structure used during crash recovery to correct data written by incomplete transactions. Modifications that did not finish updating the data files before an unexpected shutdown are replayed automatically during initialization, and before connections are accepted.

Meaning: 
- Primary logs (?).
- Stores unfinished updates of data files for crash recovery purpose.

Syncing on disk depengs on [innodb_flush_log_at_trx_commit](https://dev.mysql.com/doc/refman/5.7/en/innodb-parameters.html#sysvar_innodb_flush_log_at_trx_commit).
Role in crash-recovery: https://dev.mysql.com/doc/refman/5.7/en/innodb-recovery.html.
