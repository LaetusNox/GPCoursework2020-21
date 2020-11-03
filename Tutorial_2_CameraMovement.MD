This script is for 1st person 3D player and camera movement wherein the camera can only rotate on the Y axis and the player can only control the movement on the Z axis

Step 1:

  Right click the heirarchy and select 3D Object>Capsule and place the Camera as it's child.
  
Step 2:
    
  In the Capsule GameObject create a script component named **'Playermovement'**. Set the following variables in place:
    
    public float movespeed; // will determine movement speed
    public float rotspeed;  // will determine speed of rotation
    public float rotX;   // will show you rotation on the X axis
    public float rotY;   // will show you rotation on the Y axis (the main component)
    public float rotZ;   // will show you rotation on the Z axis
    
Step 3:

  in void update, write out:
    
    transform.Translate(0f , 0f, Input.GetAxis("Vertical") * Time.deltaTime * movespeed); // this line allows for movement on the Z-axis
        rotY += Input.GetAxis("Horizontal") * Time.deltaTime * rotspeed; // this line allows for rotation on the Y-axis, allowing the player to move on the X-axis and Z-axis at the same time

        transform.rotation = Quaternion.Euler(rotX, rotY, rotZ);
        
Step 4:

  save the script and return to unity. in the script component set numbers in the **movespeed** and **rotspeed** floats via trial and error until you get a desired movement speed
  and speed of rotation.
