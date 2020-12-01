## NGINXDirectives

Directive | Syntax | Default | Context |
---------|----------|--------- | -------- |
 absolute_redirect | absolute_redirect on | off; | absolute_redirect on; | http, server, location |
 access_log| access_log path [format [buffer=size] [gzip[=level]] [flush=time] [if=condition]];
access_log off; | access_log logs/access.log combined |  |http, server, location, if in location, limit_except
 access_log | access_log path format[buffer=size] [gzip[=level]] [flush=time] [if=condition];
access_log off; | access_log off; |  |stream, server
