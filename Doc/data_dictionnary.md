## Date dictionnary

| Entities | Attributes | Type | Description | Example |
| --- | --- | --- | --- | --- |
| Programs | program_id | SERIAL | Unique identifier for the program. | 26 |
|  | program_title | VARCHAR(255) | The unique title of the program. | "Data Science Bootcamp" |
|  | program_description | TEXT | The description of the program. | "An intensive bootcamp covering data science topics." |
|  | program_creation_date | datetime | The date the program was created | “01/02/2024” |
|  | program_modification_date | datetime | The date the program was modified | “24/05/2024” |
|  | instructor_id | INT | Unique identifier of the creator of the program. | 41 |
|  | status_id | INT | Unique identifier of the status of the program, which can be "in progress", "available", or "archived". | 1 |
|  |  |  |  |  |
| Modules | module_id | SERIAL | Unique identifier for the module. | 6 |
|  | module_title | VARCHAR(255) | The unique title of the module. | "Introduction to Python" |
|  | module_objective | TEXT | The educational objective of the module. | "Learn Python basics" |
|  | module_creation_date | datetime | The date the module was created | “01/02/2024” |
|  | module_modification_date | datetime | The date the module was modified | “24/05/2024” |
|  | status_id | INT | The status of the module, which can be "available", "in progress", or "archived". | 3 |
|  | instructor_id | INT | Unique identifier of the creator of the module. | 22 |
|  |  |  |  |  |
| Lessons | lesson_id | SERIAL | Unique identifier for the lesson. | 17 |
|  | lesson_title | VARCHAR(255) | The unique title of the lesson. | "Python Basics" |
|  | lesson_description | TEXT | The description of the lesson. | "Introduction to Python programming." |
|  | lesson_content | TEXT | At least one text content in the lesson. | "Python is a versatile language." |
|  | lesson_creation_date | datetime | The date the lesson was created | “01/02/2024” |
|  | lesson_modification_date | datetime | The date the lesson was modified | “24/05/2024” |
|  | lesson_duration | INT | The time in min to complete the lesson | 55 |
|  | status_id | INT | Unique identifier for the current status of the lesson.  | 2 |
|  | instructor_id | INT | Unique identifier for the author of the lesson.  | 18 |
|  | video_id | INT | Unique identifier for the video of the lesson.  | 45 |
|  |  |  |  |  |
| Images | image_id | INT | Unique identifier for the image. | 96 |
|  | image_title | VARCHAR(255) | The unique title of the image. | “MCD_xemple” |
|  | image_path | VARCHAR(255) | The path to access the image | “/images/python_basics.png” |
|  |  |  |  |  |
| Videos | video_id | INT | Unique identifier for the video. | 96 |
|  | video_title | VARCHAR(255) | The unique title of the video. | “resume_cours_python” |
|  | video_url | VARCHAR(255) | The url to access the video | “https://www.youtube.com/watch?v=your_video_id” |
|  |  |  |  |  |
| Instructor | instructor_id | UUID - VARCHAR(50) | Unique identifier for the instructor. | 18 |
|  | instructor_code | VARCHAR(50) | The unique code for the instructor. | "FOR18" |
|  | instructor_last_name | VARCHAR(100) | The last name of the instructor. | "Doe" |
|  | instructor_first_name | VARCHAR(100) | The first name of the instructor. | "John" |
|  | instructor_email | VARCHAR(255) | The email address used for login. | "mailto:john.doe@example.com" |
|  | instructor_password | VARCHAR(255) | The personal password for the trainer. | crypted  |
|  |  |  |  |  |
| Students | student_id | UUID - VARCHAR(50) | Unique identifier for the student. | 18 |
|  | student_registration_number | VARCHAR(50) | The unique registration number for the learner. | "APR18" |
|  | student_last_name | VARCHAR(100) | The last name of the learner. | "Smith" |
|  | student_first_name | VARCHAR(100) | The first name of the learner. | "Jane" |
|  | student_date_of_birth | DATE | The birth date of the learner. | "1990-01-01" |
|  | student_email | VARCHAR(255) | The email address used for login. | "mailto:jane.smith@example.com" |
|  | student_password | VARCHAR(255) | The personal password for the learner. | crypted |
|  | address_id | INT | The unique identifier of the address | 458 |
|  |  |  |  |  |
| Address | address_id | SERIAL | Unique identifier for the address. | 458 |
|  | address_number | INT | The number component of the address. | 123 |
|  | address_street_name | VARCHAR(255) | The street name of the address. | "Main Street" |
|  | address_zip_code | VARCHAR(10) | The ZIP or postal code of the address. | "12345" |
|  | address_city | VARCHAR(255) | The city or locality of the address. | "New York" |
|  | address_country | VARCHAR(255) | The country of the address. | "United States" |
|  |  |  |  |  |
| Administrators | admin_id | UUID - VARCHAR(50) | Unique identifier for the administrator. | 1 |
|  | admin_last_name | VARCHAR(100) | The last name of the administrator. | "Brown" |
|  | admin_first_name | VARCHAR(100) | The first name of the administrator. | "Alice" |
|  | admin_email | VARCHAR(255) | The login name for the administrator. | "alice.brown@gmail.com" |
|  | admin_password | VARCHAR(255) | The robust password for the administrator. | crypted |
|  |  |  |  |  |
| Statuses | status_id | Int | The unique ID for the status. | 2 |
|  | status_title | String | The title of the status. | "available" |
|  |  |  |  |  |
| Tags | tag_id | String | The unique ID for the tag. | 4 |
|  | tag_title | String | The title of the tag. | "Python" |