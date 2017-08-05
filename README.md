sync_slot, custom bgworker for PostgreSQL
=========================================

Background worker able to kill connections that are idle for a certain
amount of time.

This worker can use the following parameter to decide the interval of time
used to scan and kill idle connections.
- sync_slot.max_idle_time, maximum time allowed for backends to be idle
in seconds. Default set at 5s, maximum value is 3600s.

Idle backend scan is done with a loop operation on pg_stat_activity, running
at the same interval of time as the above parameter.

This worker is compatible with PostgreSQL 9.3 and newer versions.
