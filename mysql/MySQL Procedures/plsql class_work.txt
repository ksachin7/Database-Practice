mysql> create procedure getsal(inout data int)
    -> begin
    -> select sal into data from emp where empno= data;
    -> end// 
Query OK, 0 rows affected (0.01 sec)

mysql> set @data= 7782//
Query OK, 0 rows affected (0.00 sec)

mysql> call getsal(@data)//
Query OK, 1 row affected (0.00 sec)

mysql> select @data//
+-------+
| @data |
+-------+
|  2450 |
+-------+
1 row in set (0.00 sec)


mysql> create procedure findcomm(in eno int)
    -> begin
    -> declare p_sal int;
    -> declare p_comm int;
    -> 
    -> select sal into p_sal from emp where empno = eno;
    -> if p_sal>2000 then
    -> set p_comm = p_sal*0.2;
    -> else
    -> set p_comm = p_sal$0.1;
    -> end if;
    -> select p_comm;
    -> end//
Query OK, 0 rows affected (0.00 sec)

mysql> call findComm(7369) //
ERROR 1109 (42S02): Unknown table 'p_sal$0' in field list

mysql> drop procedure findcomm//
Query OK, 0 rows affected (0.00 sec)

mysql> create procedure findcomm(in eno int)
    -> begin
    -> declare p_sal int;
    -> declare p_comm int;
    -> 
    -> select sal into p_sal from emp where empno = eno;
    -> if p_sal>2000 then
    -> set p_comm = p_sal*0.2;
    -> else
    -> set p_comm = p_sal*0.1;
    -> end if;
    -> select p_comm;
    -> end//
Query OK, 0 rows affected (0.00 sec)

mysql> call findComm(7369) //
+--------+
| p_comm |
+--------+
|     80 |
+--------+
1 row in set (0.00 sec)

Query OK, 0 rows affected (0.00 sec)