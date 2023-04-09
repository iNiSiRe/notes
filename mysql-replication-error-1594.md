```
STOP SLAVE;
RESET SLAVE;
CHANGE MASTER TO MASTER_LOG_FILE='%Relay_Master_Log_File%', MASTER_LOG_POS=%Exec_Master_Log_Pos%;
START SLAVE;
```

#### In case of "DUPLICATE ..." error 1062
Add to my.cnf:
```
slave-skip-errors = 1062
```
