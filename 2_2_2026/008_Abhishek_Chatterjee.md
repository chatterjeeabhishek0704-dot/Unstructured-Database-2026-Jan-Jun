ASSIGNMENT – 2

In Mongodb compass use the CLI to
1.	Add 5 student records
a.	1 using insertOne
b.	4 using insertMany

2.	 Remove the 1st record
3.	Query for all students in “Computer” department
4.	Update “Computer” department” to “BCA”

CODE
db.students.insertOne({
  roll: 1,
  name: "Rahul",
  department: "Computer",
  age: 20
})

OUTPUT
{
acknowledged: true,
insertId: ObjectId(‘69803d9816c89e62638d3a46’)
}

CODE
db.students.insertMany([
  { roll: 2, name: "Anik", department: "Computer", age: 21 },
  { roll: 3, name: "Sujoy", department: "Mechanical", age: 22 },
  { roll: 4, name: "Pinto", department: "Computer", age: 20 },
  { roll: 5, name: "Amit", department: "Electrical", age: 23 }
])
OUTPUT
{
Acknowledged: true,
insertIds: {
‘0’: ObjectId(‘69803d9816c89e62638d3a47’),
‘1’: ObjectId(‘69803d9816c89e62638d3a48’),
‘2’: ObjectId(‘69803d9816c89e62638d3a49’),
‘3’: ObjectId(‘69803d9816c89e62638d3a4a’)
}
}
CODE
db.students.deleteOne({roll: 1 })

OUTPUT
acknowledged: true,
deletedCount: 1

CODE
db.students.find()

OUTPUT
{
_id: ObjectId(‘69803d9816c89e62638d3a47’),
roll: 2,
name: ‘Anik’,
department: ‘Computer’,
age: 21
}
{
Id: ObjectId(“69803d9816c89e62638d3a48’),
Roll: 3,
Name: ‘Sujoy’,
Department: ‘Mechanical’,
Age: 22
}
{
Id: ObjectId(69803d9816c89e62638d3a49’),
Roll: 4,
Name: ‘Pinto’,
Department: ‘Computer’,
Age: 20
}
{
Id: ObjectId(‘69803d9816c89e62638d3a4a’),
Roll: 5,
Name: ‘Amit’,
Department: ‘Electrical’,
Age: 23
}

CODE
db.students.updateMany(
  { department: "Computer" },
  { $set: { department: "BCA" } }
)
OUTPUT
{
acknowledged: true,
insertId: null,
matchedCount: 2,
modifiedCount: 2,
upsertedcount: 0
}



