# Oracle-For-Developer

#### ตรวจสอบเวอร์ชันของ Orracle

    SELECT * FROM V$INSTANCE

#### Get All Sequence 

    SELECT * FROM dba_sequences WHERE sequence_owner = 'ORGANIZATION';
    
####  dbms_output.put_line
    SET SERVEROUTPUT ON

#### Default Driver Class

    oracle.jdbc.OracleDriver
    




#### Hierarchical Queries

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
