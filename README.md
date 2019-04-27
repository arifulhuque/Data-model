# Tables explanation
The SUBJECT table has relationship with CLASS table
          SUBJECT: one SUBJECT can have one CLASS assign at a time. Therefore, it has ONE to ONE relationship.
          CLASS: one CLASS can contain one SUBJECT at a time. Therefore, it has also ONE to ONE relationship.
The TEACHER table has relationship with SUBJECT table
          TEACHER: one TEACHER can teach many SUBJECT based on the different time slot. Therefore, it has one to many relationship 
          SUBJECT: one SUBJECT can be teach by many TEACHER based on the different time slot. Therefore, it has one to many relationship
The STUDENT table has relation with SUBJECT table. 
However, many STUDENT can take many SUBJECT and many SUBJECT can be taken by many STUDENTS, STUDENT and SUBJECT tables 
have many to many relationship. To design better architecher, I have created another bridge table between STUDENT and 
SUBJECT. The table name is STUDENT_to_SUBJECT. Because of creating the STUDENT_to_SUBJECT, 
        The STUDENT table has one to many relationship with SUBJECT table
        The SUBJECT table has one to many relationship with STUDENT table
        
# Questions & ANSWERS
1. "Can you add more student (like student id 2) in subject table (like subject code 101), explain what will happen?"
--> I think, this question arised because my previous diagram was missing the bridge table. In this new diagram, I have created 
the bridge table to avoid this issue. So that I can add as many as student in my student table and connect to the subject table 
via STUDENT_to_SUBJECT table.
2. "can you assign subject to teacher without student? Try to assign, explain what will happen?"
--> yes, I can assign the subject to the teacher without student. Because, there is no relationship between teacher and 
student in the diagram.A teacher can have many subjects where student is none. In business logic, it doesn't make any sence. 
In order to teach by teacher, there has to be at least one student.
3. "can create subject without teacher and student?"
--> no, it is not possible to create a subject without teacher and student.
4. "how do you tell this class room to student/teacher based on your model ?"
--> First, a teacher needes to know what subject he/she is teaching then by the subject room number can be found.
A student also needes to know what subject he/she is taking then by the subject room number can be found.
5. "Number of student, class hour – related to subject or class room?"
--> I changed little bit in the new diagram, instade of "Number of student" I used "Number of seat" in the class table
   and class hour is related to subject.
6. "Can you explain double data type of class hour? – why do you need?"
--> The reason I have used double as a data type for class hour is, not all class hours are even number. There are few 
class hourcould be 2 hours and 25 minutes (2.25). That's why I thought double might be better data type option for class hour.
Since, there is a confusion about this data type, I have changed it to VARCHAR.
7. "All tables primary key ending with _id except subject table subject_code?"
--> Subject code is more common when it comes to subject. That's why I used subject code instead of subject id. However, in the
new diagram, I have changed it to Subject ID.
8. "Is Student grade based on subject or course?"
--> Initially, I thought, I will show the total CGPA in the Student table but to keep it simple, I have got rid of 
the grade from the student table in the new diagram. (I was considering grade as CGPA)
