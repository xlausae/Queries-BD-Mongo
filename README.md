# Queries-BD-Mongo
## 📌 Inserting Students into MongoDB with PyMongo

This code allows you to register students in a MongoDB database using Python and the **PyMongo** library.

### 🔹 What does this code do?

1. Prompts the user to enter:

   * Student's name
   * Student's age

2. Automatically sets the major to `"Data Science"`.

3. Creates a document (Python dictionary) with the student's information.

4. Inserts that document into the **Estudiantes** collection within the **BD_CursoMongo** database.

---

### 🧠 Code

```python
# Request user input
nombre = input("Enter the student's name: ")
edad = int(input("Enter the student's age: "))
carrera = "Data Science"

# Insert student
insertar_estudiante(nombre, edad, carrera)

# Function to insert a student
def insertar_estudiante(nombre, edad, carrera):
    estudiante = {
        "nombre": nombre,
        "edad": edad,
        "carrera": carrera
    }
    estudiantes.insert_one(estudiante)
    print(f"Student {nombre} inserted.")

# Select database and collection
db = cliente["BD_CursoMongo"]
estudiantes = db["Estudiantes"]
```

---

### 🗂️ MongoDB Structure

* **Database:** `BD_CursoMongo`
* **Collection:** `Estudiantes`
* **Inserted document:**

```json
{
  "nombre": "Jorge",
  "edad": 15,
  "carrera": "Data Science"
}
```

---

### 📊 Example stored records

```python
{'_id': ObjectId('69ebd3792371a22b8f99c2b0'), 'nombre': 'Jorge', 'edad': 15, 'carrera': 'Data Science'}
{'_id': ObjectId('69ebd6f32371a22b8f99c2b1'), 'nombre': 'Daniela', 'edad': 19, 'carrera': 'Data Science'}
{'_id': ObjectId('69ebd7052371a22b8f99c2b2'), 'nombre': 'Eilyn Herrera', 'edad': 19, 'carrera': 'Data Science'}
```

---

### ⚙️ Notes

* MongoDB automatically generates the `_id` field for each document.
* The `insert_one()` function inserts a single record into the collection.
* If the database or collection does not exist, MongoDB creates them automatically when the first document is inserted.

---
