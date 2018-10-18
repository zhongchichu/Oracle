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

![chaxunyi](https://github.com/zhongchichu/Oracle/blob/master/test1/img/%E7%AC%AC%E4%B8%80%E6%9D%A1%E8%AF%AD%E5%8F%A5.png)
![chaxunyi](https://github.com/zhongchichu/Oracle/blob/master/test1/img/%E7%AC%AC%E4%BA%8C%E6%9D%A1%E8%AF%AD%E5%8F%A5.png)
![chaxunyi](https://github.com/zhongchichu/Oracle/blob/master/test1/img/%E7%AC%AC%E4%B8%89%E6%9D%A1.png)
