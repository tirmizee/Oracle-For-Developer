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

## Ref

- https://oracle-base.com/articles/misc/with-clause
- https://docs.oracle.com/cd/E11882_01/server.112/e41084/functions089.htm#SQLRF30030
