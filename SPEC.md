# SPECIFICATION

- Create a web application that allows students to upload their school works.
  - Each student should have a user account
  - The teacher should have also a user account, and can create students accounts
  - Each teacher can have one or more classrooms. In each classroom can incorporate any of his students
- The teacher can create a delivery. A delivery is for a concrete classroom and has:
  - Title
  - Description
  - Deadline
  - Correction type: { None, ByTeacher, ByStudent }
  - Correction configuration
- The student can complete his/her assigned deliveries, if there are on time. 
  - To complete a delivery, the student can upload a file.
  - The file must be a .docx, .pdf, .txt or .md file
  - The student can upload a document more than one time. Each uploaded document will have a correlative version, and the deliveried work will be tha last one.
- The teacher can view the list of deliveries that has created, and the detail of each one. 
- Each assigned student from the delivery will have a:
  - State: Pending or Completed.
    - Completed works can be downloaded.
  - Grade or average grade.
  - If the correction type is ByStudent, the list of puntuactions will be shown. 

- If the delivery correction type is set to ByTeacher, the teacher set a grade to each student work.
- If the delivery correction type is set to ByStudent, each student must set a grade to their colleages. The configuration will establish how it works:

```` json
{
  "relation" : 5, -> How many people have to set a grade to each work. Must be between 1 and classroom total people count
  "notCorrectionPenalty" : 1 -> How many points will be taken if a student fails to correct each of assigned works
  "anonymous" : true -> If teacher can know who graded whom
}
````
