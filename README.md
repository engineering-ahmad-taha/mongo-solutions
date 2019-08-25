Download Robo 3t and setup it on your machine.

Create a new connection

Create a new collection (students)

Right click on the collection.

Select 'insert Document'.

Enter image description here

Paste your json data

Click validate.

Click save.

Excute your queries on the query bar.

Test your queries using robo 3t

Insert yourself as a new student. Example: {"fname" : "Ahmad","lname":"Omar","class":"A","age" :25} db.getCollection('students').insertOne({"fname" : "naaman","lname":"munther","class":"b","age" :25})

Insert the following students.

{"fname" : "Ahmad","lname":"Omar","class":"A","age" :25,"technologies":["PHP","mySql"]} {"fname" : "Ammar","lname":"Saad","class":"B","age" :23,"technologies":["PHP","MongoDB"]} {"fname" : "Steve","lname":"Rayan","class":"C","age" :18,"technologies":["C#","mySql"]} {"fname" : "Jhon","lname":"williams","class":"A","age" :30, "technologies":["Python","MongoDB"]}

db.getCollection('students').insertMany( [{"fname" : "Ahmad","lname":"Omar","class":"A","age" :25,"technologies":["PHP","mySql"]} , {"fname" : "Ammar","lname":"Saad","class":"B","age" :23,"technologies":["PHP","MongoDB"]}, {"fname" : "Steve","lname":"Rayan","class":"C","age" :18,"technologies":["C#","mySql"]}, {"fname" : "Jhon","lname":"williams","class":"A","age" :30, "technologies":["Python","MongoDB"]}})

Write a MongoDB query to update the data of all students by incrementing their ages one year..
db.students.updateMany(({}),{ $inc: { age: +1} })

Write a MongoDB query to update all the student who has (ADAM) name and make thier classs A and thier technolgies ['PHP','mySql'].
db.students.updateMany(({fname:"ADAM"}),{ class:'A', technolgies:['PHP','mySql'] })

Write a MongoDB query to delete one student from class A .
db.students.update({fname:"Adam"},{$set: { class:'A', technologies :['PHP','mySql'] }})

Write a MongoDB query to delete All the students from class C.
db.students.delete({class:"C"})

Write a MongoDB query to display all the students that thier age less than 20.
db.students.delete({age:{ $lt: 20 }})

Write a MongoDB query to display all the students that thier age greater than 30.
db.students.find({age:{ $gt: 20 }})

Write a MongoDB query to get only the students of class B.
db.students.find({class:'B'})

Sort the faculty details by their age (descending order) and get the details of the first five faculty members only. .
db.students.find({}).sort({age:-1}).limit(5)