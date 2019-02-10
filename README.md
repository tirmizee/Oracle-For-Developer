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
