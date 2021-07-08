    select a.sid||'|'|| a.serial#||'|'|| a.process
    from v$session a, v$locked_object b, dba_objects c
    where b.object_id = c.object_id
    and a.sid = b.session_id
    and OBJECT_NAME=upper('&TABLE_NAME');

    alter session kill session 'sid,serial#' immediate;

### Reference

- https://orahow.com/find-and-remove-table-lock-in-oracle/
