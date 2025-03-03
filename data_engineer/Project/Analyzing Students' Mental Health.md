![image](https://github.com/user-attachments/assets/f08be827-3b09-49e5-afb0-26e5a7c35fcc)

Does going to university in a different country affect your mental health? A Japanese international university surveyed its students in 2018 and published a study the following year that was approved by several ethical and regulatory boards.

The study found that international students have a higher risk of mental health difficulties than the general population, and that social connectedness (belonging to a social group) and acculturative stress (stress associated with joining a new culture) are predictive of depression.


Explore the `students` data using PostgreSQL to find out if you would come to a similar conclusion for international students and see if the length of stay is a contributing factor.

Here is a data description of the columns you may find helpful.

| Field Name    | Description                                      |
| ------------- | ------------------------------------------------ |
| `inter_dom`     | Types of students (international or domestic)   |
| `japanese_cate` | Japanese language proficiency                    |
| `english_cate`  | English language proficiency                     |
| `academic`      | Current academic level (undergraduate or graduate) |
| `age`           | Current age of student                           |
| `stay`          | Current length of stay in years                  |
| `todep`         | Total score of depression (PHQ-9 test)           |
| `tosc`          | Total score of social connectedness (SCS test)   |
| `toas`          | Total score of acculturative stress (ASISS test) |


## DataFram available as `students`
```SQL
-- Run this code to view the data in students
SELECT *
FROM students;
```
![image](https://github.com/user-attachments/assets/00da858d-f228-451f-ac60-cfb668ab9360)
![image](https://github.com/user-attachments/assets/cb3e2903-e954-4457-81cf-1b12b5d536e1)
![image](https://github.com/user-attachments/assets/2bdd2206-2a49-4b0a-8136-bc88b58b4294)
![image](https://github.com/user-attachments/assets/892ffc20-db6e-46d3-b1cd-50502d5fc586)
![image](https://github.com/user-attachments/assets/53a5157a-7e0a-4bd6-bde6-102881ec7c80)


## DataFram available as `df`
```SQL
SELECT stay AS stay, COUNT(stay) AS count_int,ROUND(AVG(todep),2) AS average_phq, ROUND(AVG(tosc),2) AS average_scs, ROUND(AVG(toas),2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```

![image](https://github.com/user-attachments/assets/f8ca50a2-7034-4568-8590-2de88663bdb0)
![image](https://github.com/user-attachments/assets/d7d7c0a1-cb0e-412c-a590-d4aca1bef437)
