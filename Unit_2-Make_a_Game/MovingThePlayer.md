Here's a simplified, step-by-step version of the tutorial to make it easier for students to follow:

---

### **Moving the Player in Unity**
**Level:** Beginner | **Time:** ~30 minutes | **XP:** +10  

#### **1. Add a Rigidbody to the Player**
1. Select the **Player** GameObject in the **Hierarchy**.
2. In the **Inspector**, click **Add Component** → Search for **Rigidbody** → Add it.  
   ✅ *Make sure to select "Rigidbody" (not "Rigidbody 2D").*

#### **2. Install the Input System Package**
1. Open **Window > Package Manager**.
2. In the **Packages** dropdown, select **Unity Registry**.
3. Find **Input System** and click **Install**.
4. If prompted, enable the system and restart Unity.  

#### **3. Add a Player Input Component**
1. Select the **Player** GameObject.
2. In the **Inspector**, click **Add Component** → **Player Input**.
3. Click **Create Actions**, then:
   - Make a new folder called **"Input"**.
   - Save the new input asset as **"InputActions"**.

#### **4. Create a PlayerController Script**
1. In the **Project** window, create a folder named **"Scripts"**.
2. Select the **Player**, then **Add Component > New Script**.
3. Name it **PlayerController** and move it to the **Scripts** folder.
4. Double-click the script to open it in Visual Studio.

#### **5. Write the OnMove Function**
1. **Delete** the `Update()` function from the script.
2. **Add the InputSystem namespace** at the top:
   ```csharp
   using UnityEngine.InputSystem;
   ```
3. **Create the OnMove function**:
   ```csharp
   void OnMove(InputValue movementValue)
   {
   }
   ```

#### **6. Apply Input Data to the Player**
1. **Inside** `OnMove`, add:
   ```csharp
   Vector2 movementVector = movementValue.Get<Vector2>(); 
   ```
2. **Above** `Start()`, declare a Rigidbody variable:
   ```csharp
   private Rigidbody rb;
   ```
3. **Inside** `Start()`, assign the Rigidbody:
   ```csharp
   rb = GetComponent<Rigidbody>();
   ```
4. **Create a FixedUpdate function**:
   ```csharp
   private void FixedUpdate() 
   {
   }
   ```

#### **7. Apply Force to Move the Player**
1. **Inside** `FixedUpdate`, add:
   ```csharp
   rb.AddForce(movementVector);
   ```
2. **Above `Start()`**, declare movement variables:
   ```csharp
   private float movementX;
   private float movementY;
   ```
3. **Inside `OnMove()`**, assign values:
   ```csharp
   movementX = movementVector.x;
   movementY = movementVector.y;
   ```
4. **Modify `FixedUpdate()`**:
   ```csharp
   Vector3 movement = new Vector3(movementX, 0.0f, movementY);
   rb.AddForce(movement);
   ```

#### **8. Fix the Player’s Speed**
1. **Above `Start()`**, add a speed variable:
   ```csharp
   public float speed = 0;
   ```
2. **Modify `AddForce()` in `FixedUpdate()`**:
   ```csharp
   rb.AddForce(movement * speed);
   ```
3. **In the Inspector**, set **Speed = 10**.
4. **Test the game** – the player should move at a reasonable speed!

---

This version keeps everything structured and easy to follow. Let me know if you'd like further adjustments! 🚀
