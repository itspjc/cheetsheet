# Cheetsheet for Database management


## Postgres
- start postgres service : `service postgresql restart`
- connect with postgres using psql: `psql -h 10.146.0.3 -U app -d lge-pri`



- Drop all tables
```
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;
```
- add primary key column
```
ALTER TABLE algorithm_association ADD COLUMN algorithm_association_id SERIAL PRIMARY KEY;
```

- reset sequence
```
ALTER SEQUENCE <시퀀스 이름 기본 값은 테이블이름_seq> RESTART WITH 0 INCREMENT 4;
# e.g ALTER SEQUENCE login_login_id_seq RESTART WITH 1
```

- show all sessions connecting with specific database
```
SELECT client_addr, pg_terminate_backend(pid)
FROM pg_stat_activity 
WHERE pid <> pg_backend_pid()
AND datname = 'piealpha';
```

- show session information
```
SELECT client_addr FROM pg_stat_activity;
```
