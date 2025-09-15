# 📚 MongoDB_25  
This repo is used for my **MongoDB personal project**  

---

## 🚀 MongoDB + Mongoose Practice  

This repository contains my MongoDB practice projects using **Mongoose** in **Node.js**.  
It is designed as a quick reference for:  

- 🛠️ **MongoDB shell commands**  
- 💡 **Mongoose basics**  
- 🔄 **Common operations like CRUD**  

---

## 📌 1. Project Details  

**Tech Stack**:  
- Node.js  
- MongoDB  
- Mongoose  

**Purpose**:  
Learn MongoDB fundamentals, practice queries, and understand how to use **Mongoose** as an ODM (Object Data Modeling library).  

**Topics Covered**:  
- MongoDB database creation and basic commands  
- Collections and documents  
- CRUD operations  
- Using Mongoose for schema and model management  

---

## 📌 2. MongoDB Useful Commands  

### 👉 Database Commands  

```bash
# Show all databases
show dbs

# Switch to (or create) a database
use myDatabase

# Show current database
db
```

### 👉 Collection Commands

```bash
# Show collections
show collections

# Create collection
db.createCollection("students")

# Drop collection
db.students.drop()
```

### 👉 Insert Documents

```bash
# Insert one document
db.students.insertOne({ name: "Alice", grade: "10", age: 15 })

# Insert many documents
db.students.insertMany([
  { name: "Bob", grade: "9", age: 14 },
  { name: "Charlie", grade: "11", age: 16 }
])
```

### 👉 Read Documents

```bash
# Find all
db.students.find()

# Find one
db.students.findOne()

# Find with condition
db.students.find({ grade: "10" })

# Comparison operators
db.students.find({ age: { $gt: 14 } })   # age > 14
db.students.find({ age: { $lt: 18 } })   # age < 18
```

### 👉 Update Documents

```bash
# Update one
db.students.updateOne(
  { name: "Alice" },
  { $set: { grade: "11" } }
)

# Update many
db.students.updateMany(
  { grade: "9" },
  { $set: { grade: "10" } }
)
```

### 👉 Delete Documents

```bash
# Delete one
db.students.deleteOne({ name: "Alice" })

# Delete many
db.students.deleteMany({ grade: "9" })
```

## 📌 3. Mongoose Basics

### 👉 Installation

```bash
npm install mongoose
```

### 👉 Connect to MongoDB

```bash
const mongoose = require('mongoose');

mongoose.connect('mongodb://127.0.0.1:27017/myDatabase', {
  useNewUrlParser: true,
  useUnifiedTopology: true
})
.then(() => console.log("✅ MongoDB connected"))
.catch(err => console.log("❌ Connection error:", err));
```

### 👉 Define Schema & Model

```bash
// Schema
const studentSchema = new mongoose.Schema({
  name: String,
  grade: String,
  age: Number
});

// Model
const Student = mongoose.model("Student", studentSchema);
```