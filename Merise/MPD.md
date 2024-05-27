
```SQL
--Script PosteGRE


CREATE TABLE Images(
   image_id SERIAL NOT NULL,
   image_title VARCHAR(250)  NOT NULL,
   image_path VARCHAR(250)  NOT NULL,
   PRIMARY KEY(image_id),
   UNIQUE(image_title)
);

CREATE TABLE Videos(
   video_id SERIAL NOT NULL,
   video_title VARCHAR(250)  NOT NULL,
   video_url VARCHAR(250)  NOT NULL,
   PRIMARY KEY(video_id),
   UNIQUE(video_title)
);

CREATE TABLE Administrators(
   admin_id UUID DEFAULT uuid_generate_v4() NOT NULL,
   admin_last_name VARCHAR(100)  NOT NULL,
   admin_first_name VARCHAR(100)  NOT NULL,
   admin_email VARCHAR(255)  NOT NULL,
   admin_password VARCHAR(255)  NOT NULL,
   PRIMARY KEY(admin_id)
);

CREATE TABLE Tags(
   tag_id SERIAL NOT NULL,
   tag_title VARCHAR(100)  NOT NULL,
   PRIMARY KEY(tag_id)
);

CREATE TABLE Instructors(
   instructor_id UUID DEFAULT uuid_generate_v4() NOT NULL,
   instructor_code VARCHAR(250)  NOT NULL,
   instructor_last_name VARCHAR(100)  NOT NULL,
   instructor_first_name VARCHAR(100)  NOT NULL,
   instructor_email VARCHAR(50)  NOT NULL,
   instructor_password VARCHAR(250)  NOT NULL,
   PRIMARY KEY(instructor_id),
   UNIQUE(instructor_code)
);

CREATE TABLE Statuses(
   status_id SERIAL NOT NULL,
   status_title VARCHAR(100)  NOT NULL,
   PRIMARY KEY(status_id)
);

CREATE TABLE Address(
   address_id SERIAL NOT NULL,
   address_number INTEGER NOT NULL,
   address_street_name VARCHAR(255) NOT NULL,
   address_zip_code VARCHAR(10) NOT NULL,
   address_city VARCHAR(100) NOT NULL,
   address_country VARCHAR(100) NOT NULL,
   PRIMARY KEY(address_id)
);

CREATE TABLE Programs(
   program_id SERIAL NOT NULL,
   program_title VARCHAR(250)  NOT NULL,
   program_description TEXT NOT NULL,
   program_creation_date TIMESTAMP NOT NULL,
   program_modification_date TIMESTAMP,
   status_id INTEGER NOT NULL,
   instructor_id VARCHAR(50)  NOT NULL,
   PRIMARY KEY(program_id),
   FOREIGN KEY(status_id) REFERENCES Statuses(status_id),
   FOREIGN KEY(instructor_id) REFERENCES Instructors(instructor_id)
);

CREATE TABLE Lessons(
   lesson_id SERIAL NOT NULL,
   lesson_title VARCHAR(250)  NOT NULL,
   lesson_description VARCHAR(250)  NOT NULL,
   lesson_duration INTEGER NOT NULL,
   lesson_content TEXT NOT NULL,
   lesson_creation_date TIMESTAMP NOT NULL,
   lesson_modification_date TIMESTAMP,
   lesson_version VARCHAR(50) NOT NULL, 
   status_id INTEGER NOT NULL,
   instructor_id VARCHAR(50)  NOT NULL,
   video_id INTEGER NOT NULL,
   PRIMARY KEY(lesson_id),
   FOREIGN KEY(status_id) REFERENCES Statuses(status_id),
   FOREIGN KEY(instructor_id) REFERENCES Instructors(instructor_id),
   FOREIGN KEY(video_id) REFERENCES Videos(video_id)
);

CREATE TABLE Modules(
   module_id SERIAL NOT NULL,
   module_title VARCHAR(250)  NOT NULL,
   module_objective TEXT NOT NULL,
   module_creation_date TIMESTAMP NOT NULL,
   module_modification_date TIMESTAMP,
   module_version VARCHAR(50)  NOT NULL,
   status_id INTEGER NOT NULL,
   instructor_id VARCHAR(50)  NOT NULL,
   PRIMARY KEY(module_id),
   FOREIGN KEY(status_id) REFERENCES Statuses(status_id),
   FOREIGN KEY(instructor_id) REFERENCES Instructors(instructor_id)
);

CREATE TABLE Students(
   student_id UUID DEFAULT uuid_generate_v4() NOT NULL,
   student_registration_number VARCHAR(50)  NOT NULL,
   student_last_name VARCHAR(100)  NOT NULL,
   student_first_name VARCHAR(100)  NOT NULL,
   student_date_of_birth DATE NOT NULL,
   student_email VARCHAR(255)  NOT NULL,
   student_password VARCHAR(255)  NOT NULL,
   address_id INTEGER NOT NULL,
   PRIMARY KEY(student_id),
   UNIQUE(student_registration_number),
   FOREIGN KEY(address_id) REFERENCES Address(address_id)
);

CREATE TABLE Contain(
   program_id INTEGER NOT NULL,
   module_id INTEGER NOT NULL,
   PRIMARY KEY(program_id, module_id),
   FOREIGN KEY(program_id) REFERENCES Programs(program_id),
   FOREIGN KEY(module_id) REFERENCES Modules(module_id)
);

CREATE TABLE Include(
   lesson_id INTEGER NOT NULL,
   module_id INTEGER NOT NULL,
   PRIMARY KEY(lesson_id, module_id),
   FOREIGN KEY(lesson_id) REFERENCES Lessons(lesson_id),
   FOREIGN KEY(module_id) REFERENCES Modules(module_id)
);

CREATE TABLE Own(
   image_id INTEGER NOT NULL,
   lesson_id INTEGER NOT NULL,
   PRIMARY KEY(image_id, lesson_id),
   FOREIGN KEY(image_id) REFERENCES Images(image_id),
   FOREIGN KEY(lesson_id) REFERENCES Lessons(lesson_id)
);

CREATE TABLE Belong_to(
   tag_id INTEGER NOT NULL,
   module_id INTEGER NOT NULL,
   PRIMARY KEY(tag_id, module_id),
   FOREIGN KEY(tag_id) REFERENCES Tags(tag_id),
   FOREIGN KEY(module_id) REFERENCES Modules(module_id)
);

CREATE TABLE Validate(
   lesson_id INTEGER NOT NULL,
   student_id VARCHAR(50) NOT NULL,
   validated BOOLEAN NOT NULL,
   PRIMARY KEY(lesson_id, student_id),
   FOREIGN KEY(lesson_id) REFERENCES Lessons(lesson_id),
   FOREIGN KEY(student_id) REFERENCES Students(student_id)
);

CREATE TABLE Take(
   program_id INTEGER NOT NULL,
   student_id VARCHAR(50) NOT NULL,
   PRIMARY KEY(program_id, student_id),
   FOREIGN KEY(program_id) REFERENCES Programs(program_id),
   FOREIGN KEY(student_id) REFERENCES Students(student_id)
);
```