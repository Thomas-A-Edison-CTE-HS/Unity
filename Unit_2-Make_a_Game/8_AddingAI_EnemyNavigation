# Adding AI Navigation in Unity

## Overview
In this tutorial, you will:
- Implement a NavMesh for AI-based enemy navigation.
- Add static and dynamic obstacles to challenge the player.
- Code win and lose conditions using Unity scripting.

### Prerequisites
- Basic understanding of Unity
- Familiarity with C# scripting
- Unity version 2022.3 or later

---

## Steps to Implement AI Navigation

### 1. Install the AI Navigation Package
1. Open **Window > Package Manager**.
2. From the **Packages** dropdown, select **Unity Registry**.
3. Search for **AI Navigation**.
4. Select the package and click **Install**.

### 2. Create an Enemy
1. Create an empty **GameObject** and rename it to `Enemy`.
2. Reset its **Transform** component.
3. Add a **Cube** as a child, rename it `EnemyBody`, and set its scale to `(0.5, 1, 0.5)`.
4. Create and assign a material to `EnemyBody`.

### 3. Bake a NavMesh
1. Select the **Ground** GameObject.
2. In the **Inspector**, click **Add Component > NavMeshSurface**.
3. Click **Bake**.
4. Expand the **Object Collection module** and set **Collect Objects** to **Current Object Hierarchy**.
5. Click **Bake** again.

### 4. Make the Enemy Chase the Player
1. Select the `Enemy` GameObject.
2. Add a **NavMeshAgent** component.
3. Set **Speed** to around `2.5`.
4. Create a new script **EnemyMovement.cs** and add the following:
```csharp
using UnityEngine;
using UnityEngine.AI;

public class EnemyMovement : MonoBehaviour
{
    public Transform player;
    private NavMeshAgent navMeshAgent;

    void Start()
    {
        navMeshAgent = GetComponent<NavMeshAgent>();
    }

    void Update()
    {
        if (player != null)
        {
            navMeshAgent.SetDestination(player.position);
        }
    }
}
```
5. Assign the `Player` GameObject to the **player** variable in the Inspector.
6. Run the game to test.

### 5. Create Static Obstacles
1. Create a **Cube** and modify its shape.
2. Drag obstacles under **Ground** in the Hierarchy.
3. Select **Ground** and click **Bake** in the **NavMeshSurface** component.
4. Adjust **Agent Type** settings for step height and slope.
5. Test the game.

### 6. Create Dynamic Obstacles
1. Create a **Cube**, rename it `DynamicBox`, and add a **Rigidbody** with **Mass = 0.1**.
2. Add a **NavMeshObstacle** component and enable **Carve**.
3. Turn it into a **Prefab**.
4. Duplicate and place multiple instances in the scene.
5. Test the game.

### 7. Set Win and Lose Conditions
1. Open `PlayerController.cs` and add:
```csharp
private void OnCollisionEnter(Collision collision)
{
    if (collision.gameObject.CompareTag("Enemy"))
    {
        Destroy(gameObject);
        winTextObject.gameObject.SetActive(true);
        winTextObject.GetComponent<TextMeshProUGUI>().text = "You Lose!";
    }
}
```
2. Add an **Enemy** tag to `EnemyBody`.
3. Update the win condition:
```csharp
void SetCountText()
{
    countText.text = "Count: " + count.ToString();
    if (count >= 12)
    {
        winTextObject.SetActive(true);
        Destroy(GameObject.FindGameObjectWithTag("Enemy"));
    }
}
```
4. Test the game.

---

## Conclusion
By completing this tutorial, you have successfully implemented AI navigation in Unity, allowing enemies to chase the player while avoiding static and dynamic obstacles. You have also implemented win and lose conditions to complete the gameplay loop. 🎮🚀

