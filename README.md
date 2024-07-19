# University-ERP-System-Database-Schema-Documentation

### Overview

This document describes the database schema for a University ERP (Enterprise Resource Planning) system. The schema supports key university operations such as student enrollment, course management, faculty management, and reporting.


## Database Schema
### Tables and Relationships

![image](https://github.com/vchukwuma/University-ERP-System-Database-Schema-Documentation/blob/main/University%20DB%20Schema%20Design.png?raw=true)


### Usage

This schema is designed to provide a structured and efficient way to manage university data. It supports various operations such as tracking student enrollments, managing course offerings, recording exam results, and producing reports for decision-making.

### Example Queries

- Retrieve all students enrolled in a specific course:

```sql

SELECT s.first_name, s.last_name
FROM students s
JOIN enrollments e ON s.stu_id = e.stu_id
WHERE e.cour_id = :cour_id;
```

- Get the list of instructors in a specific department:

```sql

SELECT i.first_name, i.last_name
FROM instructors i
JOIN departments d ON i.inst_id = d.head_of_department
WHERE d.depart_id = :depart_id;
```

- Generate a grade report for a student:

 ```sql

SELECT c.course_name, g.grade_value
FROM grades g
JOIN enrollments e ON g.enroll_id = e.enroll_id 
JOIN courses c ON e.cour_id = c.cour_id
WHERE e.stu_id = :stu_id;
```

### Conclusion

This database schema serves as a foundational structure for managing university operations effectively. By utilizing this schema, you can ensure data consistency, integrity, and accessibility across various university functions.






