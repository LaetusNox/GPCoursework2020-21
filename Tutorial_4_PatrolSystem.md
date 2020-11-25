Step 1:

Create a 3D object in whatever shape you like and create a script component.

Step 2:

Open the script component and add the variables:

    public float speed;
    public float waitTime;
    public float startWaitTime;
    public Transform[] patrolPoint; // this array will be how you set patrol points in your unity project without editting the script with every new point
    public int index; //this is the numerical variable regarding how many points are in your array
    
Step 3:

In **void Start()**, write out:

    waitTime = startWaitTime; //this makes the two aforementioned variables equal the same thing, allowing for a sense of regularity in the game
    index = Random.Range(0, patrolPoint.Length); // this makes the int variable **Index** randomly select any of the points in the **patrolPoints** array
    
Step 4:

In **void Update()** the bulk of the code can be found. Here you will need to input:

    transform.position = Vector3.MoveTowards(transform.position, patrolPoint[index].position, speed * Time.deltaTime); 
    // this causes the game object previously made (your patroller) to move towards one of the points in the patrolPoint[] array. 
    // As a Vector3, you need to ensure that there is '.position' after '*transform.position*' and '*patrolPoint[index].position*' or there will be a vector error  

        if (Vector3.Distance(transform.position, patrolPoint[index].position) < 0.2f)
        // if the game object is 0.2 frames (or less) away from the patrol point--
        //the 0.2f is done because unity is incredibly precise and if the patroling 3d object is even 0.0001f off mark, then it will not register the movement as complete
        {
            if (waitTime <= 0) // and if the wait time is less than or equal to 0--
            {
                index = Random.Range(0, patrolPoint.Length); // a new point will be selected
                waitTime = startWaitTime; // and the wait time will be reset

            }
            else
            {

                waitTime -= Time.deltaTime; //otherwise, keep counting down on the wait time
            }
        }    
        
        
Step 5:

Save your script and return to unity. Here you will be able to see that the script has a new public float to set the **Start Wait Time**, so set it with a time as necessary.
A good value to start with is 2, as any longer can be a little long, but the value is something to experiment with.

Step 6:

Go to the GameObject menu and select Create empty. Instead of setting a 3d model, set an icon/gizmo in the inspector so you can see a visual of the game object and 
set it in a place where you want one of the patrol points. Copy and paste this gameObject however many times you wish and place them as you wish, these will be your 
patrol points.

Step 7:

In the Heirarchy, select the 3D gameObject that has the script component and in the size float, type in how many empty gameObjects you have made for the patrol points. 
Open the array settings and drag the empty gameObjects into the array. Now you have a working patrol system that randomly selects a point before moving to it, waiting, and 
randomly selecting another point
