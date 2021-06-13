#### JDBC URL Format

    jdbc:oracle:thin://<host>:<port>/<service>
    jdbc:oracle:thin:<host>:<port>:<SID><br> 
    jdbc:oracle:thin:<TNSName> (from 10.2.0.1.0)

#### JDBC URL Example

    jdbc:oracle:thin:@mimmi:1521:ORCL_SID
    jdbc:oracle:thin:@192.168.1.12:1521/ORCL_SVC
    jdbc:oracle:thin:@(description=(address=(host=localhost)(protocol=tcp)(port=1521))(connect_data=(sid=ORCL)))
    jdbc:oracle:thin:@ML
