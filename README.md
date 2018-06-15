# Oracle Notes

- Continuous Query Notification (https://docs.oracle.com/cd/B28359_01/appdev.111/b28424/adfns_cqn.htm#BDCGGACA)


# 12c Features

## Sequence as Default Value 

```sql
Create sequence seq_t start with 1 increment 1 nocycle;
Create table t_my_tab (id number default seq_t.nextval primary key)
```

## Invisible column
Another new feature is we can define a table column as invisible columm. when we define column as invisible it is not being fetched when we use generic query like "select * from" . It can be queried by only direct usage like "select invcolumn from ..". This feature is useful especially when we dont need that column instead of drop it or some security reasons for example password column etc.

```sql
ALTER TABLE t_my_tab  MODIFY (pwd invisible);
```