Step 1:

  To start making a button prompt, begin by right clicking the **Heirarchy** go down to **UI** and select **Canvas**.

Step 2:

  Right click again and create **UI>Image** (henceforth referred to as **Prompt Image**) and UI>text (referred to as **Prompt Text**). 
Insert whatever text you would like and rename them as you will, placing the Prompt Text game object as a child of the Prompt Image. 

Step 3:

Create 2 3d Objects, a cube and a capsule. In the Cube's inspector, click the Tag dropdown menu and select **create tag**. From there create and assign it the tag **'Collect**  
Step 4:
  
  In the Capsule's inspector, create a new script called **'RaycastButtonPrompt'** and establish the following classes:
  
    public float Light; //this is so you can edit the length of the raycast in unity without having to open the script
    public Image prompt;
    public bool prompton;
    
Step 5: 

  In Void Update () begin the establishing line of your raycast
  
     RaycastHit hit;
        Ray PromptRay = new Ray(transform.position, Vector3.forward); //this creates your ray

        Debug.DrawRay(transform.position, transform.forward * Light); //this establishes the length of your ray and allows you to see it in the scene
        
Step 6:

  From here, we add in the section of script that activates and deactivates the button prompt accordingly:
  
     prompt.gameObject.SetActive(false); //this sets the button prompt game objects (Prompt Image and Prompt Text) as inactive 

        if (Physics.Raycast(PromptRay, out hit, Light)) 

        {

            if (hit.collider.tag == "collect") //if the ray hits any gameobject tagged with "collect"

            {
              prompton = true; //then the bool prompton will be set to true

                if (prompton == true)
                {
                    prompt.gameObject.SetActive(true); //when the bool prompton is true, then the button prompt game objects will be active and visible
                }


                if (Input.GetKeyDown(KeyCode.Space)) 

                {
                    Destroy(hit.transform.gameObject); // destroy the object hit when the spacebar is pressed.
                    prompton = false;
                }

            }
        }
