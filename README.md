# unity_3d_snake_game_arcore

## Steps
### 1. Create the snake head prefab, and tag it as the player

### 2. Create the SnakeMovement.cs to enable the mouse control
- Inside the SnakeMovement.cs, create MoveForward(), Rotation() methods.
- Add a method CameraFollow() to make the camera follow the movement, find the GameObject with tag "MainCamera"
- Use Vecotor3.SmoothDamp to make the transform smooth

### 3. Create the SnakeBody prefab
- in the SnakeMovement.cs, create an array of transform to store the the body position
- have the bodyparts follow the head

### 4. Create SnakeBody.cs
- have the head and bodyparts know its own order
- refer the head position by FindGameObjectWithTag("Player") as transform
- refer the bodyParts list of transform by GetComponent<SnakeMovement>().bodyparts
- use for loop to iterate each element of the array list
- assign the iterator i(index) to the myOrder index
- myOrder == 0, it is the first bodypart, will follow the head, make it look at the head, transform.LookAt(head.transform.position
- else myOrder == other, make it follow the previous one, myOrder-1; transform.LookAt(head.tansform.position)

### 5. Eat the orbs to grow body
- create a cube as the orb, tag it as Orb
- in SnakeMovement.cs, add a new method, call the existed method, OnCollisionEnter(Collision other)
- if(other.transform.tag == "Orb") Destroy(other.gameObject);
- transform the newbodyPart to the Head, Transform newBodyPart = Instantiate(bodyObject, currentPos, Quaternion.identity) as transform
- bodyParts.Add(newBodyPart), increment the list or transform
- Note: add rigidbody to enable collision, leave the bodyParts size to be 0
