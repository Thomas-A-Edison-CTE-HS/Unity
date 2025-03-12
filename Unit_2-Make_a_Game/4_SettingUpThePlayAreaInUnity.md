# **Setting Up the Play Area in Unity**  

## **Overview**  
In this tutorial, you’ll:  
✅ Create and configure a wall  
✅ Duplicate and position walls to enclose the play area  

By the end, your game will have a defined play area with walls to keep the player contained.  

---

## **1. Create a Wall for the Play Field**  
1️⃣ **Create an empty parent GameObject:**  
   - **Right-click** in the **Hierarchy** window → **Create Empty**  
   - Rename it **Walls**  
   - In the **Inspector**, reset its **Transform**  

2️⃣ **Create a Wall child GameObject:**  
   - **Right-click** in the **Hierarchy** window → **3D Object** → **Cube**  
   - Rename it **West Wall**  
   - Reset its **Transform** in the **Inspector**  
   - Drag **West Wall** onto **Walls** to make it a child  

3️⃣ **Set the Wall’s Transform values:**  
   - Press **F** to focus on **West Wall** in the **Scene** view  
   - Set **Scale** to **(X: 0.5, Y: 2.0, Z: 20.5)**  
   - Set **Position X** to **-10** to align it to the edge  

4️⃣ **Create a material for the walls:**  
   - In the **Project** window, go to the **Materials** folder  
   - **Right-click** → **Create** → **Material**, name it **Walls**  
   - In the **Inspector**, set **Base Map RGB** to **(79, 79, 79)** for dark gray  
   - Set **Metallic Map** to **0** and **Smoothness** to **0.25** for a matte finish  
   - Drag **Walls** material onto **West Wall** in the **Scene**  

---

## **2. Finish the Play Field Walls**  
1️⃣ **Create the East Wall:**  
   - **Right-click** **West Wall** → **Duplicate**  
   - Rename it **East Wall**  
   - In the **Inspector**, remove the negative sign from **Position X**  

2️⃣ **Create the North & South Walls:**  
   - **Duplicate** **East Wall**, rename it **North Wall**  
   - Set **Rotation Y** to **90**  
   - Set **Position X** to **0**, **Position Z** to **10**  
   - **Duplicate** **North Wall**, rename it **South Wall**  
   - Set **Position Z** to **-10**  

---

## **3. Test the Game**  
▶️ **Play the game** and make sure the ball stays inside the walls.  
❌ If the ball passes through walls, **disable** the **IsTrigger** property in the **Collider** component.  

Now your game has a properly enclosed play area! 🎮🚀
