# MongoDB

```bash
Last login: Tue Jun 21 14:39:09 on ttys000
sachin@SMacBook ~ % mongo
MongoDB shell version v5.0.7
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("f107bd6d-5dd3-48d8-8bc7-fb23c6e01854") }
MongoDB server version: 5.0.7
```

---

```sql
> show dbs
admin    0.000GB
company  0.000GB
config   0.000GB
local    0.000GB
mydb     0.000GB
```

```sql
> use company
switched to db company
> db
company
```

```sql
db.employees.insertOne(
{
ename:'JONES',
job:'MANAGER',
sal:2975,
}
);
```

```sql
db.employees.insertOne (
{
ename:'MARTIN',
job:'SALESMAN',
sal:1250,
hiredate:'28/09/1981',
comm:1400,
deptno:30
}
);
```

```sql
db.employees.insertOne (
{
ename:'BLAKE',
job:'MANAGER',
sal:2850,
hiredate:'01/05/1981',
deptno:30
}
);
```

```sql
db.employees.insertOne (
{
ename:'CLARK',
job:'MANAGER',
sal:2450,
hiredate:'09/06/1981',
deptno:10
}
);
```

```sql
db.employees.insertOne (
{
ename:'SCOTT',
job:'ANALYST',
sal:3000,
hiredate:'19/04/1987',
deptno:20
}
);
```

```sql
db.employees.insertOne (
{
ename:'KING',
job:'PRESIDENT',
sal:5000,
hiredate:'17/11/1981',
deptno:10
}
);
```

```sql
db.employees.insertOne (
{
ename:'TURNER',
job:'SALESMAN',
sal:1500,
hiredate:'08/09/1981',
deptno:30
}
);
```

```sql
db.employees.insertOne (
{
ename:'ADAMS',
job:'CLERK',
sal:1100,
hiredate:'23/05/1987',
deptno:20
}
);
```

```sql
db.employees.insertOne (
{
ename:'JAMES',
job:'CLERK',
sal:950,
hiredate:'03/12/1981',
deptno:30
}
);
```

```sql
db.employees.insertOne (
{
ename:'FORD',
job:'ANALYST',
sal:3000,
hiredate:'03/12/1981',
deptno:20
}
);
```

```sql
db.employees.insertOne (
{
ename:'MILLER',
job:'CLERK',
sal:1300,
hiredate:'23/01/1982',
deptno:10
}
);
```

```sql
db.employees.find().pretty()

{ "_id" : ObjectId("62b198d484e031f489a40ef3") }
{
	"_id" : ObjectId("62b198f484e031f489a40ef4"),
	"ename" : "WARD",
	"job" : "SALESMAN",
	"sal" : 1250,
	"hiredate" : "22/02/1981",
	"comm" : 500,
	"deptno" : 30
}
{
	"_id" : ObjectId("62b1a030df472f4194c178ea"),
	"ename" : "JONES",
	"job" : "MANAGER",
	"sal" : 2975
}
{
	"_id" : ObjectId("62b1a030df472f4194c178eb"),
	"ename" : "MARTIN",
	"job" : "SALESMAN",
	"sal" : 1250,
	"hiredate" : "28/09/1981",
	"comm" : 1400,
	"deptno" : 30
}
{
	"_id" : ObjectId("62b1a030df472f4194c178ec"),
	"ename" : "BLAKE",
	"job" : "MANAGER",
	"sal" : 2850,
	"hiredate" : "01/05/1981",
	"deptno" : 30
}
{
	"_id" : ObjectId("62b1a030df472f4194c178ed"),
	"ename" : "CLARK",
	"job" : "MANAGER",
	"sal" : 2450,
	"hiredate" : "09/06/1981",
	"deptno" : 10
}
{
	"_id" : ObjectId("62b1a030df472f4194c178ee"),
	"ename" : "SCOTT",
	"job" : "ANALYST",
	"sal" : 3000,
	"hiredate" : "19/04/1987",
	"deptno" : 20
}
{
	"_id" : ObjectId("62b1a030df472f4194c178ef"),
	"ename" : "KING",
	"job" : "PRESIDENT",
	"sal" : 5000,
	"hiredate" : "17/11/1981",
	"deptno" : 10
}
{
	"_id" : ObjectId("62b1a030df472f4194c178f0"),
	"ename" : "TURNER",
	"job" : "SALESMAN",
	"sal" : 1500,
	"hiredate" : "08/09/1981",
	"deptno" : 30
}
{
	"_id" : ObjectId("62b1a030df472f4194c178f1"),
	"ename" : "ADAMS",
	"job" : "CLERK",
	"sal" : 1100,
	"hiredate" : "23/05/1987",
	"deptno" : 20
}
{
	"_id" : ObjectId("62b1a030df472f4194c178f2"),
	"ename" : "JAMES",
	"job" : "CLERK",
	"sal" : 950,
	"hiredate" : "03/12/1981",
	"deptno" : 30
}
{
	"_id" : ObjectId("62b1a030df472f4194c178f3"),
	"ename" : "FORD",
	"job" : "ANALYST",
	"sal" : 3000,
	"hiredate" : "03/12/1981",
	"deptno" : 20
}
{
	"_id" : ObjectId("62b1a030df472f4194c178f4"),
	"ename" : "MILLER",
	"job" : "CLERK",
	"sal" : 1300,
	"hiredate" : "23/01/1982",
	"deptno" : 10
}
```

```sql
db.employees.find().pretty().count()
13
```

```sql
—- dropping database —-
mydb> use new
switched to db new

new> show collections
std
student

new> db.dropDatabase();
{ ok: 1, dropped: 'new' }
new> show collections;

new> show dbs;
admin     40.00 KiB
company   72.00 KiB
config   108.00 KiB
local     40.00 KiB
mydb     184.00 KiB
```

```sql
—- dropping collection —-
mydb> show collections;
employees
movie
student

mydb> db.employees.find().pretty();
[ { _id: ObjectId("62b19e699f17ec55a143e7e5") } ]

mydb> db.employees.drop();
true

mydb> db.employees.find().pretty();

mydb> show collections;
movie
student
```