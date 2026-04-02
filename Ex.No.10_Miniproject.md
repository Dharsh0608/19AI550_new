# Ex.No: 10  Implementation of 2D/3D game -------------------
### DATE:                                                                           
### REGISTER NUMBER :212224220022 
### AIM: 
To develop a Escape from the Falling Object Game in Unity
### Algorithm:
```
1. Create a new Unity project.
2. Add a Player GameObject to the scene.
3. Add a FallingObject GameObject to the scene.
4. Attach the PlayerController script to the Player GameObject.
5. Attach the FallingObject script to the FallingObject GameObject.
6. Set the Player GameObject's tag and add a Collider2D (if needed).
7. Set the Ground GameObject with tag "Ground" and add a Collider2D with IsTrigger enabled.
8. In the PlayerController script, read horizontal input and move the player each frame (in Update).
9. In the FallingObject script, move the object downwards each frame and check for collision with the ground using OnTriggerEnter2D.
10. If the falling object collides with the ground, destroy the player object.
```  
### Program:
```
using UnityEngine;

public class FallingObject : MonoBehaviour
{
    public float fallSpeed = 1f;

    void Update()
    {
        transform.position += new Vector3(0, -fallSpeed * Time.deltaTime, 0);
    }

    void OnTriggerEnter2D(Collider2D other)
    {
        if (other.gameObject.CompareTag("Ground"))
        {
            Destroy(gameObject); // Destroy the object when it hits the ground
        }
    }
}

```
```

using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float move = Input.GetAxis("Horizontal"); // Get left/right key input
        transform.position += new Vector3(move * speed * Time.deltaTime, 0, 0);
    }
}

```
### Output:
<img width="1280" height="678" alt="image" src="https://github.com/user-attachments/assets/86bdd978-4edd-4ef5-88e4-95459c18a2fe" />

<img width="1280" height="679" alt="image" src="https://github.com/user-attachments/assets/70e410ac-1f22-4f0d-ba20-a69d96e936ed" />

<img width="1280" height="677" alt="image" src="https://github.com/user-attachments/assets/904ecb56-6d34-42e1-9f8c-5e39810063f0" />


### Result:
Thus the game Escape from the Falling Object Game was developed using Unity.
