---
banner: https://images.pexels.com/photos/531880/pexels-photo-531880.jpeg?cs=srgb&dl=pexels-pixabay-531880.jpg&fm=jpg
banner_y: "58.5"
sticker: lucide//home
color:
---
# Courses
```dataview
table
from "My Courses" WHERE file.name != "My Courses"
sort title desc
```
---
# Upcoming assignments

```dataview
table due as "Due Date", completed as "Completed"
from "Assignments"
where completed = "no"
sort due asc

```
---
# Upcoming exams

```dataview
table date as "Exam date", completed as "Completed"
from "Exams"
where completed = "no"
sort date asc

```
