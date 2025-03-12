# **Creating Collectibles in Unity**

## **Overview**
In this tutorial, you will:
✅ Create a PickUp GameObject for the player to collect
✅ Write a script to rotate the collectible
✅ Turn the PickUp GameObject into a Prefab
✅ Instantiate multiple collectibles around the play area

By the end, your game will have interactive collectibles that enhance gameplay! 🎮✨

---
## **1. Create a Collectible GameObject**
### **Step 1: Create a PickUp Object**
1. In the **Hierarchy** window, **Right-click** → **3D Object** → **Cube**
2. Rename it **PickUp**
3. Reset the **Transform** component
4. Press **F** to frame the **PickUp** in the **Scene** view
5. Move it so it does not overlap with the **Player**

### **Step 2: Set Transform Values**
1. Set **Position Y** to **0.5** (to sit above the ground)
2. Set **Rotation (X, Y, Z)** to **(45, 45, 45)** (tilt the cube)
3. Set **Scale (X, Y, Z)** to **(0.5, 0.5, 0.5)** (make it smaller)

### **Step 3: Create a PickUp Material**
1. In the **Project** window, find the **Background** material
2. **Right-click** → **Duplicate** and rename it **PickUp**
3. Set **Base Map RGB** to **(255, 200, 0)** for a bright yellow
4. Drag the **PickUp** material onto the **PickUp GameObject**

---
## **2. Rotate the PickUp GameObject**
### **Step 1: Create a New Script**
1. Select **PickUp** in the **Hierarchy**
2. In the **Inspector**, click **Add Component** → **New Script**
3. Name it **Rotator**
4. Move it to the **Scripts** folder in the **Project** window
5. Open **Rotator.cs** for editing

### **Step 2: Modify the Script**
1. Remove the **Start()** function (it’s not needed)
2. Inside **Update()**, add:
   ```csharp
   using UnityEngine;
   
   public class Rotator : MonoBehaviour
   {
       void Update()
       {
           transform.Rotate(new Vector3(15, 30, 45) * Time.deltaTime);
       }
   }
   ```
3. Save the script and return to Unity

---
## **3. Make PickUp a Prefab**
### **Step 1: Convert PickUp to a Prefab**
1. In the **Project** window, create a **Prefabs** folder
2. Drag **PickUp** from the **Hierarchy** into the **Prefabs** folder
3. Select **Original Prefab** when prompted

### **Step 2: Enter and Exit Prefab Editing Mode**
1. Click the **arrow** next to the **PickUp** GameObject in the **Hierarchy** to enter prefab mode
2. Use the **back arrow** at the top of the **Hierarchy** window to return to the Scene view

---
## **4. Add More Collectibles**
### **Step 1: Create a Parent GameObject**
1. In the **Hierarchy** window, **Right-click** → **Create Empty**
2. Rename it **PickUp Parent**
3. Reset its **Transform**
4. Drag **PickUp** under **PickUp Parent**

### **Step 2: Align to a Top View**
1. Click the **Gizmo** in the top-right of the **Scene** view to switch to **top-down view**
2. Zoom out to see the entire play area

### **Step 3: Duplicate PickUps**
1. Move the first **PickUp** where you want it
2. Select **PickUp**, press **Ctrl+D** (Mac: **Cmd+D**) to duplicate
3. Move the duplicate to another location
4. Repeat until you have enough collectibles in the scene

### **Step 4: Test the Game**
▶️ Play the game and check if the **PickUps** rotate and remain collectable.
❌ If they act as solid obstacles, disable their **Collider’s IsTrigger** property.

Now your game has fully functional collectibles! 🎉

