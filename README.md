PostgreSQLP3ForSqueak can connect PostgreSQL by protocol version3.
It can SELECT, INSERT, UPDATE and DELETE.
It can catch error code and mesasge.
It can do COPY IN and COPY OUT.
It can react NOTIFY.
It covers binary data.

Sample is below.
MD5 initialize. 
params := ConnectionParameterSetP3 new
    host: 'localhost';
    databaseName: 'postgres';
    port: 5432;
    userName: 'postgres';
    password: 'postgres'.

connection := PostgreSQLP3Connection using: params.
connection prepareQuery: 'SELECT * FROM pg_tables'.
connection bind: #() statement: nil portal: nil.
connection describe: nil type: #portal.
connection execute: nil maxRows: 0.
result := connection sync.
answer := PostgreSQLP3Answer parse: result.
connection close
