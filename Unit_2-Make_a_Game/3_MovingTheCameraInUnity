
# **Moving the Camera in Unity**  

## **Overview**  
In this tutorial, you’ll:  
✅ Set the Camera position  
✅ Write a script to make the Camera follow the Player sphere with a fixed offset  

By the end, your game’s camera will smoothly follow the player.

---

## **1. Set the Camera Position**  
1️⃣ Select the **Main Camera** in the **Hierarchy** window.  
2️⃣ Set the **Y position** to **10** and **X rotation** to **45** for a better angle.  
3️⃣ (Optional) Drag the **Main Camera** onto the **Player GameObject** in the Hierarchy to make it a child.  
   - Test the game to see how the camera moves with the player.  
   - Undo this by dragging the camera back above the Player GameObject.  

---

## **2. Create the CameraController Script**  
1️⃣ Select **Main Camera** → **Add Component** → **New Script**.  
2️⃣ Name it **CameraController** and move it to the **Scripts** folder.  
3️⃣ Open the script and add:  

```csharp
using UnityEngine;

public class CameraController : MonoBehaviour
{
    public GameObject player; // Reference to player
    private Vector3 offset; // Camera offset from player

    void Start()
    {
        offset = transform.position - player.transform.position; // Set initial offset
    }

    void LateUpdate()
    {
        transform.position = player.transform.position + offset; // Maintain offset
    }
}
```

---

## **3. Reference the Player GameObject**  
1️⃣ Save the script and go back to Unity.  
2️⃣ Select **Main Camera** in the **Hierarchy**.  
3️⃣ Drag the **Player GameObject** into the **Player** slot in the **CameraController** component.  

---

## **4. Test the Game**  
▶️ Press **Play** and watch the camera follow the player! 🎮  

Now your camera smoothly tracks the player while maintaining a fixed distance. 🚀
