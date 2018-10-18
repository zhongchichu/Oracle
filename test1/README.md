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

优化指导：为数据库创建一个或多个索引来改进当前语句的执行计划。
查询语句二：

~~~sql
SELECT d.department_name ,count(e.job_id)as "部门总人数" ,
avg(e.salary)as "平均工资"
FROM hr.departments d ,hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT' ,'Sales');
~~~
查询结果：

![chaxunyi](https://github.com/zhongchichu/Oracle/blob/master/test1/img/%E7%AC%AC%E4%BA%8C%E6%9D%A1%E8%AF%AD%E5%8F%A5.png)


优化指导：无

自定义语句：

~~~sql
SELECT d.department_name ,count(e.job_id)as "部门总人数" ,
avg(e.salary)as "平均工资"
FROM hr.departments d, hr.employees e
WHERE d.department_id = e.department_id
and d.department_name = 'IT' or d.department_name = 'Sales'
GROUP BY department_name
~~~

查询结果：

![chaxunyi](https://github.com/zhongchichu/Oracle/blob/master/test1/img/%E7%AC%AC%E4%B8%89%E6%9D%A1.png)

优化指导：取消where语句处大量的笛卡尔积操作

总结：
感觉教材上面第二条语句最好，因为没有给出优化指导。
