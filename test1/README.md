查询语句一：

```sql
SELECT d.department_name ,count(e.job_id)as "部门总人数" ,
avg(e.salary)as "平均工资"
from hr.departments d ,hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT' ,'Sales')
GROUP BY department_name;
```
查询结果：

![chaxunyi]()
