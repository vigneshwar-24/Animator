# Animator
## Aim:
To develop a animator using unity.

## Algorithm:
### Step 1: 
Download 2 crouch idle from maximo 3d. Drag it and drop it in unity asset.
### Step 2: 
Select one crouch and in the inspector choose rig-> Animation type (humaniod) and then click update.
### Step 3: 
Perform the step 2 for another crouch
### Step 4: 
Select one crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 5: 
Perform the step 4 for another crouch
### Step 6: 
Drag one crouch, put it in hierarchy and name it as Player.
### Step 7: 
In the Player inspector we have Animator. Right click in Assets-> create -> Animator Controller (name it as IdleToCrouch)
### Step 8: 
Drag the IdleToCrouch to the Controller option under the Animator in the inspector. Click that IdleToCrouch , a window opens and select parameter tab , create 2 parameter, InputX and InputY
### Step 9: 
Select the another crouch and attach with Entry button and name it as movement. Right click it and choose create blend tree.
### Step 10: 
Click the movement button, blend tree opens. Choose InputY in parameter and under the motion click ‘+’ sign and choose add the motion field twice.
### Step 11: 
Drag the second crouch and put it motion field, then drag the first crouch and put it in the another motion field.
### Step 12: 
Uncheck the automata threshold and change the values -1 and 0 in first column( priority for the crouch). Create a C# file and name it as IdleToCrouch, drag it to the player
### Step 13: 
Download a walking crouch from maximo 3d and drag it into unity. In the inspector select rig-> animation types(humanoid) -> Apply
### Step 14: 
Select the crouch and in the inspector choose Animation-> Root transform rotation-> Based upon (original)  and check the Loop Time and click apply
### Step 15: 
In blend tree, in blend type choose (2D Freedom Directional), parameter (InputX, InputY) , one crouch (0,-1,1) and walking (1,0,1). Bring the camera under the player 

## Program:
### IdleToCrouch
```python
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class idleToCrouch : MonoBehaviour
{
    public Animator animator;
    public float InputX;
    public float InputY;
    // Start is called before the first frame update
    void Start()
    {
        animator = this.gameObject.GetComponent<Animator>();
    }

    // Update is called once per frame
    void Update()
    {
        InputY = Input.GetAxis("Vertical");
        InputX = Input.GetAxis("Horizontal");
        animator.SetFloat("InputY",InputY);
        animator.SetFloat("InputX", InputX);
    }
}
```

## Output:
### CROUCHING:
![Screenshot (55)](https://user-images.githubusercontent.com/75235488/174804261-c9913d66-4929-422e-82e2-5a118155771e.png)

### WALKING
![Screenshot (56)](https://user-images.githubusercontent.com/75235488/174804304-8762c6a2-e250-47f5-9169-45e7b904abe2.png)



## Result:
Animator using unity is developed successfully.
