 -  Fixed `getSyslogSink()` sending no further records once it had failed to
    send one, such as while the syslog server was unreachable, and raising an
    unhandled promise rejection for every record logged after that.  The sink
    now reconnects on the next record, including after the server closes a TCP
    connection, and reports the first failure to the meta logger.  Records
    that were waiting to be sent when a send fails are dropped, so that records
    logged during an outage aren't sent long after they were logged.
