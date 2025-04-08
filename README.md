# blender
blender_workshop

# 🧊 Cube Distribution and Composition Addon (Blender)

This Blender addon enables users to:

- 📦 Distribute cubes in a visually organized grid layout  
- 🗑️ Delete selected cubes from the scene  
- 🔗 Compose (merge) adjacent cubes by removing shared faces  


## 🚀 Features

### 1. Distribute Cubes
- Input a number (1–19)
- Click **Distribute Cubes**
- Cubes are added in a clean square grid layout inside a dedicated collection `Task1_Cubes`

### 2. Delete Selected Cubes
- Select one or more cubes
- Click **Delete Cubes**
- Removes them from the scene

### 3. Compose Adjacent Cubes
- Select **two adjacent cubes**
- Click **Compose Mesh**
- Removes shared face and merges the meshes into a single object


## ⚙️ Technical Components

### 🧩 Property Group
- Task1Properties: Stores number of cubes to be generated
- ✅ Validates:
  - Natural numbers only
  - Maximum limit of 19
  - Provides UI error feedback


### 🔧 Operators

#### `DistributeCubesOperator`
- Places cubes in a square grid layout
- Avoids overlapping using a set of occupied positions
- Reuses or creates the `Task1_Cubes` collection for clean organization

#### `DeleteCubesOperator`
- Deletes only if at least one object is selected
- Provides Blender error messages if no selection

#### `ComposeMeshOperator`
- Validates mesh objects and their adjacency
- Uses face center comparison with tolerance
- Joins meshes and deletes shared face
- Merges duplicate vertices to clean geometry

---

## 🧪 Error Handling

- ❗ Input Validation:
  - Enforces range and type checks
  - Reports errors through Blender's report system
- ❗ Operation Validation:
  - Mesh type and selection checks
  - Adjacency validation for composition
- ❗ Exception Handling:
  - Prevents crashes due to invalid selections
  - All operations fail gracefully with user feedback

---

## 🖥️ UI Overview

- Accessible in **3D Viewport** → Sidebar → **Custom Tab**
- Controls:
  - Number input field
  - `Distribute Cubes` button
  - `Delete Cubes` button
  - `Compose Mesh` button with help text

---

## ✅ Best Practices Followed

- ⚙️ Proper mode switching between Object/Edit
- 🎯 Clean selection handling
- 📁 Scene hierarchy management using dedicated collections
- 🧼 Mesh cleanup using `remove_doubles`

---

## 📌 Usage Summary

| Task                 | Steps                                                                 |
|----------------------|------------------------------------------------------------------------|
| **Distribute Cubes** | Enter 1–19 → Click `Distribute Cubes`                                  |
| **Delete Cubes**     | Select cubes → Click `Delete Cubes`                                    |
| **Compose Mesh**     | Select 2 adjacent cubes → Click `Compose Mesh`                         |

---

## 🧾 License

This project is for educational/demo purposes. Customize and reuse as needed.
