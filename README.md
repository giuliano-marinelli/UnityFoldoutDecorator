# UnityFoldoutDecorator
Foldout as a Decorator for group variables in Unity Script Inspector with options for:

* change foldout name.
* apply foldout to one or to many variables
* set variables as read only
* use styled or default editor versions

![Preview](https://user-images.githubusercontent.com/5109640/132052832-8a50bbc2-5c90-4037-b926-cc6da6cf6c2e.png)

## How to

### Install
Download and copy the **Editor** and **Inspector** folders into your Project Assets.

### Use

Just put the decorator above the variable and set the options you want:
```csharp
[Foldout("Name", foldEverything = true, styled = true, readOnly = true)]
```

Example (same as image above):
```csharp
public class MyScript : MonoBehaviour
{
    [Foldout("One styled with read only", foldEverything = false, styled = true, readOnly = true)]
    public float speed = 1f;
    public float retractSpeed = 1f;
    
    [Foldout("Styled ones", styled = true)]
    public float climbSpeed = 1f;
    public float nodeDistance = 2f;
    public float minDistance = 2f;
    
    [Foldout("Only this", false)]
    public int maxAmountNodes = 20;
    public GameObject nodePrefab;
    
    [Foldout("This and this", false)]
    public LayerMask hookableLayer;
    [Foldout("This and this", false)]
    public LayerMask collibleLayer;

    [Foldout("A group")]
    public Vector2 direction;
    public GameObject player;
    public GameObject spawn;

    [Foldout("Read only things", readOnly = true)]
    public bool done = false;
    public bool connected = false;
    public bool retracting = false;
    public bool climbing = false;
}
```
