## Rapidly provision Oracle Fusion Middleware 12c Services
Project to rapidly provision an Oracle Fusion Middleware service using Docker Compose.

### Pre-requisites
`docker build --shm-size=2g --force-rm --rm=true --no-cache -t oracledb -f database/Dockerfile.12.1.0.2.160119 database`

`docker build --shm-size=2g --force-rm --rm=true --no-cache -t wccontent -f wccontent/Dockerfile.12.2.1.0.0 wccontent`

`docker run -i -P --name=db --shm-size=1g -t database`

`docker run -i -P --name=ucm --shm-size=1g -t wccontent`

`docker run -i -P --name=ibr --shm-size=1g -t wccontent`

`/usr/bin/python create_schemas.py -f /u01/app/oracle/middleware -c 172.17.0.2:1521:orcl -m DEV1 em ucm capture wccadf`

`/usr/bin/python drop_schemas.py -f /u01/app/oracle/middleware -c 172.17.0.2:1521:orcl -m DEV1 --all`

`/u01/app/oracle/middleware/oracle_common/common/bin/wlst.sh create_domain_off.py -h /tmp/mydomain1 -c 172.17.0.2:1521:orcl -m DEV1 --db_password welcome1 --nm_password welcome1 --as_password welcome1 ucm capture wccadf ibr`

`/u01/app/oracle/middleware/oracle_common/common/bin/wlst.sh add_servers_onl.py -a 172.17.0.3 -h /tmp/mydomain1 --use_plain --as_password welcome1 ucm`

`/u01/app/oracle/middleware/oracle_common/common/bin/wlst.sh add_servers_onl.py -a 172.17.0.3 -h /tmp/mydomain1 --use_plain --as_password welcome1 ibr`

--add-host host:ip
-h hostname
--hostname hostname