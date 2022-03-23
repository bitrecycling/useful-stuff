# useful-stuff

brain-outsourcing: a collection of stuff I use and tend to forget.

## Check spring sessions interacted in the last N minutes
```
SELECT * FROM (SELECT TO_CHAR(sysdate, 'YYYYMMDDHH24MISS') as CUR, TO_CHAR(LAST_ACCESS_TIME / (1000 * 60 * 60 * 24)
                                  + TO_DATE('1970-01-01 01:00:00', 'YYYY-MM-DD HH:MI:SS') ,
        'YYYYMMDDHH24MISS') as LAT from SPRING_SESSION) where LAT > CUR-N00 //replace N with Minutes
  ```
