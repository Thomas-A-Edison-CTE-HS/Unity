**Unity Tutorial: Detecting Collisions with Collectibles**

**Overview**
In this tutorial, you will learn how to:
- Modify the PlayerController script so that PickUp GameObjects disappear upon collision with the Player sphere.
- Use tags and conditional statements to ensure only PickUp objects disappear.
- Configure colliders as triggers and add a Rigidbody component for proper functionality.

---

### **Step 1: Disable PickUps with OnTriggerEnter**
1. Open the **PlayerController** script.
2. Below the `FixedUpdate` function, add the `OnTriggerEnter` function:
    ```csharp
    void OnTriggerEnter(Collider other)
    {
    }
    ```
3. Inside the function, disable the collided object:
    ```csharp
    other.gameObject.SetActive(false);
    ```
   _Note: No visible change will occur until we configure PickUps as triggers._

---

### **Step 2: Add a Tag to the PickUp Prefab**
1. In the **Project** window, navigate to the **Prefabs** folder and select the **PickUp** prefab.
2. In the **Inspector**, locate the **Tag** dropdown and click **Add Tag**.
3. Click the **+ (Add)** button and create a new tag named `PickUp` _(case-sensitive)_.
4. Assign the **PickUp** tag to the prefab.

---

### **Step 3: Write a Conditional Statement**
1. Open **PlayerController** script.
2. Modify `OnTriggerEnter` to check for the `PickUp` tag before disabling objects:
    ```csharp
    void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.CompareTag("PickUp"))
        {
            other.gameObject.SetActive(false);
        }
    }
    ```
3. Save the script and return to Unity.

---

### **Step 4: Set the Pickup Colliders as Triggers**
1. In the **Project** window, select the **PickUp** prefab.
2. In the **Inspector**, locate the **Box Collider** component.
3. Enable the **Is Trigger** checkbox.
4. Save and enter **Play Mode** to test. The PickUp GameObjects should now disappear on collision!

---

### **Step 5: Add a Rigidbody Component to the PickUp Prefab**
1. In the **Project** window, select the **PickUp** prefab.
2. In the **Inspector**, click **Add Component** and select **Rigidbody**.
3. Disable **Use Gravity** and enable **Is Kinematic**.
4. Save and test in **Play Mode** to confirm correct behavior.

---

### **Final Script Example**
```csharp
using UnityEngine;
using UnityEngine.InputSystem;

public class PlayerController : MonoBehaviour
{
    private Rigidbody rb;
    private float movementX;
    private float movementY;
    public float speed = 0;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void OnMove(InputValue movementValue)
    {
        Vector2 movementVector = movementValue.Get<Vector2>();
        movementX = movementVector.x;
        movementY = movementVector.y;
    }

    private void FixedUpdate()
    {
        Vector3 movement = new Vector3(movementX, 0.0f, movementY);
        rb.AddForce(movement * speed);
    }

    void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.CompareTag("PickUp"))
        {
            other.gameObject.SetActive(false);
        }
    }
}
```

By completing these steps, your game will now detect and disable collectibles upon collision with the Player. Happy coding! 🚀

