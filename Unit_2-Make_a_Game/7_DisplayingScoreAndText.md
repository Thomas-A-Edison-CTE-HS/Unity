# Unity Tutorial: Displaying Score and Text

## Overview
In this tutorial, you will:
- Modify the `PlayerController` script to store the number of collected PickUp objects.
- Create and configure UI Text elements to display:
  - The count value
  - A game end message
 
---
## Step 1: Store the Value of Collected PickUps

1. **Declare a new count variable:**
   - Open the `PlayerController` script.
   - Add the following line below the Rigidbody variable declaration:
     ```csharp
     private int count;
     ```

2. **Initialize the count variable:**
   - Inside the `Start` function, initialize `count` to 0:
     ```csharp
     count = 0;
     ```

3. **Increment the count variable:**
   - Inside `OnTriggerEnter`, after deactivating the PickUp object, add:
     ```csharp
     count = count + 1;
     ```

---
## Step 2: Create a UI Text Element

1. **Add a Text object:**
   - Right-click in the `Hierarchy` window > UI > Text - TextMeshPro.
   - If prompted, import `TMP Essentials`.
   - Rename the Text GameObject to `CountText`.

2. **Preview the full canvas in 2D view:**
   - Select `Canvas` in the `Hierarchy`.
   - Press `F` to frame it in the Scene view.
   - Toggle `2D` mode.

3. **Edit the text:**
   - Select `CountText`, replace “New Text” with “Count: 0”.

4. **Position the text:**
   - Open `Rect Transform` settings.
   - Hold `Shift+Alt` (or `Option` on Mac) and set the anchor to the upper-left.
   - Adjust `Pos X = 10`, `Pos Y = -10`.

---
## Step 3: Display the Count Value

1. **Import `TMPro` Library:**
   - Add at the top of `PlayerController.cs`:
     ```csharp
     using TMPro;
     ```

2. **Declare a text variable:**
   - Under the speed variable, add:
     ```csharp
     public TextMeshProUGUI countText;
     ```

3. **Create a `SetCountText` function:**
   ```csharp
   void SetCountText()
   {
       countText.text = "Count: " + count.ToString();
   }
   ```

4. **Call `SetCountText` in `Start` and `OnTriggerEnter`:**
   ```csharp
   SetCountText();
   ```

5. **Assign the `CountText` in the Inspector:**
   - Drag the `CountText` GameObject to the `countText` slot in `PlayerController`.

6. **Update the Event System:**
   - In `Hierarchy`, select `EventSystem`.
   - Click `Replace with InputSystem-UI-InputModule` if needed.

---
## Step 4: Create a Game End Message

1. **Create a new text GameObject:**
   - Right-click `Hierarchy` > UI > Text - TextMeshPro.
   - Rename it `WinText`.
   - Set text to "You Win!", color to black, size to 32, and alignment to center.
   - Position `Pos X = 0`, `Pos Y = 100`.

2. **Declare a variable for `WinText` in `PlayerController.cs`:**
   ```csharp
   public GameObject winTextObject;
   ```

3. **Disable `WinText` at start:**
   ```csharp
   winTextObject.SetActive(false);
   ```

4. **Display `WinText` when all pickups are collected:**
   - Modify `SetCountText()`:
     ```csharp
     if (count >= 12) {
         winTextObject.SetActive(true);
     }
     ```
   *(Adjust `12` to match the number of pickups in your game.)*

5. **Assign `WinText` in the Inspector:**
   - Drag the `WinText` GameObject to the `winTextObject` slot in `PlayerController`.

6. **Test Your Game!**
   - Start at `0` and increase by `1` per pickup.
   - The "You Win!" message should appear when all pickups are collected.

---
## Final `PlayerController.cs` Script
```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.InputSystem;
using TMPro;

public class PlayerController : MonoBehaviour
{
    private Rigidbody rb;
    private int count;
    private float movementX;
    private float movementY;
    public float speed = 0;
    public TextMeshProUGUI countText;
    public GameObject winTextObject;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
        count = 0;
        SetCountText();
        winTextObject.SetActive(false);
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
            count = count + 1;
            SetCountText();
        }
    }

    void SetCountText()
    {
        countText.text = "Count: " + count.ToString();
        if (count >= 12)
        {
            winTextObject.SetActive(true);
        }
    }
}
```
---

🎉 **Congratulations!** Your game now displays the score and a winning message. 🚀

