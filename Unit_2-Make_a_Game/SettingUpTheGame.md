**Step-by-Step Student Activity Guide: Setting Up the Game in Unity**

**Objective:**
By the end of this activity, you will set up the basic environment for a simple game using Unity.

---

## **Step 1: Overview**
In this activity, you will:
- Create a new Unity project.
- Set up a game environment.
- Add objects and colors.
- Adjust lighting for better visibility.

**Estimated Time:** 20 minutes  
**Skill Level:** Beginner  

---

## **Step 2: Before You Begin**
### **What You Need:**
- A computer with Unity installed (latest version recommended: Unity 6).
- Unity Hub and an active Unity account.
- Basic knowledge of navigating the Unity interface (if new, visit Unity's tutorial on getting started).

---

## **Step 3: Create a New Unity Project**
1. Open **Unity Hub** and log in.
2. Click **New Project**.
3. Choose **Universal 3D** template.
4. Name your project **Rollaball**.
5. Choose a folder to save your project.
6. Click **Create Project**.

Once the project loads, you will see an empty scene.

---

## **Step 4: Create a New Scene**
1. Go to **Layout** and choose **Default Layout**.
2. Click **File > New Scene**.
3. Select **Basic URP Template**.
4. Click **Create**.
5. Save the scene: Click **File > Save As**, name it **MiniGame**, and save it in the **Scenes** folder.

---

## **Step 5: Create a Ground Plane**
1. Click **GameObject > 3D Object > Plane**.
2. In the **Hierarchy** window, rename it **Ground**.
3. In the **Inspector** window, reset the **Transform** position to (0,0,0).
4. Press **F** to center the view on the plane.

---

## **Step 6: Scale the Ground Plane**
1. Select the **Ground** object.
2. Press **R** to activate the **Scale Tool**.
3. Drag the **X (red)** and **Z (blue)** handles to enlarge the plane.
4. Set **X and Z Scale** values to **2.0** in the **Inspector**.

---

## **Step 7: Create a Player GameObject**
1. Right-click in the **Hierarchy** window > **3D Object > Sphere**.
2. Rename it **Player**.
3. In the **Inspector**, reset **Transform** to (0,0,0).
4. Change **Y Position** to **0.5** so it sits on the plane.
5. Press **F** to frame the view on the player.

---

## **Step 8: Adjust Default Lighting**
1. Click **Directional Light** in the **Hierarchy**.
2. In the **Inspector**, expand the **Light component**.
3. Change **Color** to **white** using the color picker.
4. Set **RGB values** to **255,255,255**.

---

## **Step 9: Add Colors with Materials**
### **Create a Materials Folder**
1. In the **Project** window, right-click **Assets > Create > Folder**.
2. Rename the folder **Materials**.

### **Create and Apply Background Material**
1. In **Materials**, right-click > **Create > Material**.
2. Rename it **Background**.
3. In the **Inspector**, adjust the **Base Map color** to gray (RGB: 130,130,130).
4. Drag the material onto the **Ground** in the **Scene** view.

### **Create and Apply Player Material**
1. Create another material and name it **Player**.
2. Set **Base Map color** to light blue (RGB: 0,220,255).
3. Drag the **Player** material onto the **sphere** in the **Scene** view.

---

## **Final Steps: Adjust Directional Light Rotation**
1. Select **Directional Light** in the **Hierarchy**.
2. In **Transform**, change **Rotation** to **X=50, Y=50, Z=0**.

---

## **Checkpoint: What Should Your Scene Look Like?**
- A gray **Ground** plane.
- A light blue **Player** sphere centered on the plane.
- Proper lighting for a clear and bright scene.

Congratulations! You have successfully set up your Unity game environment! 🎮

