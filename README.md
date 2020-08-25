# Oracle-Document

#ตรวจสอบเวอร์ชันของ Orracle

SELECT * FROM V$INSTANCE

# Tricker Aotu Generate ID For v11g

create or replace TRIGGER  "INSERT_ROLE"

    BEFORE INSERT ON ROLE
    FOR EACH ROW
    DECLARE
      role_id number;
    BEGIN
      SELECT demo_cust_seq.nextval
        INTO role_id
        FROM dual;
      :new.ROLE_ID := role_id;
    END;
    
 # Create Sequence Generate ID
    
    CREATE SEQUENCE supplier_seq
        MINVALUE 1
        START WITH 1
        INCREMENT BY 1
        CACHE 20;

# Get All Sequence 

    SELECT * FROM dba_sequences WHERE sequence_owner = 'ORGANIZATION';
    
#  dbms_output.put_line
    SET SERVEROUTPUT ON

#### Default Driver Class

    oracle.jdbc.OracleDriver
    
#### JDBC URL Format

    jdbc:oracle:thin://<host>:<port>/<service><br> jdbc:oracle:thin:<host>:<port>:<SID><br> 
    jdbc:oracle:thin:<TNSName> (from 10.2.0.1.0)

#### Example

    jdbc:oracle:thin:@mimmi:1521:ORCL_SID
    jdbc:oracle:thin:@192.168.1.12:1521/ORCL_SVC
    jdbc:oracle:thin:@(description=(address=(host=localhost)
    (protocol=tcp)(port=1521))(connect_data=(sid=ORCL)))
    jdbc:oracle:thin:@ML

### Hierarchical Queries

<p align="center">
    <img width="50%" src="https://user-images.githubusercontent.com/15135199/86520737-094fdf00-be72-11ea-9b08-c2e5ea991e2e.png">
</p>

    SELECT 
        emp_id,
        emp_first_name,
        CONNECT_BY_ROOT emp_first_name as MANAGER_NAME,
        LEVEL
    FROM employee
    WHERE LEVEL > 1 
    CONNECT BY PRIOR emp_id = manager_id
    ORDER SIBLINGS BY emp_id;

.

    SELECT 
        emp_id,
        LEVEL,
        SYS_CONNECT_BY_PATH(emp_first_name, '/') "Path"
    FROM employee
    CONNECT BY PRIOR emp_id = manager_id
    ORDER SIBLINGS BY emp_id;
    
#### Self Join (Join ตัวเอง)   
    

## Ref

- https://oracle-base.com/articles/misc/with-clause
- https://docs.oracle.com/cd/E11882_01/server.112/e41084/functions089.htm#SQLRF30030
