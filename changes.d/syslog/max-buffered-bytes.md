 -  Added `SyslogSinkOptions.maxBufferedBytes` option, which limits the total
    size of the messages waiting to be sent.  When a record would go over that
    limit, the oldest records waiting are dropped to make room, and a warning
    is logged to the meta logger.
