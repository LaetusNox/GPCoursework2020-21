Step 1:
 
Open a new unity project
  
Step 2: 
 
Right click the ``Heirarchy tab``, go down to ``UI`` and select ``Canvas``
  
Step 3:

Right click the ``Heirarchy tab`` and select ``empty GameObject`` and make it a child of the **Canvas**. Rename it to whatever you like but from henceforth, it will be referred to as ``Progress Bar`` 
 
Step 4:

Right click the **Progress Bar** in the Heirarchy Tab and create a new ``UI>Image``, henceforth known as ``Frame``. In the image component of the **Frame** Game Object, select an empty bar graphic of your choice. This will be the frame of the progress bar.
  
Step 5:

Right click the Heirarchy and select ``UI>Image`` again, and make it a child of the **Progress Bar**. This new image gameObject will be referred to as ``Fill``. From here, reshape the **Progress Bar** Parent GameObject to the general size you want. 

Step 6:

In the Inspector under the Rect Transform for the two children GameObjects (**Frame** and **Fill**), click the ``Anchor Select``. Hold Alt down, go down to the 'Stretch' section and select the option ``Fill to Parent``.

Step 7:

Select the **Progress Bar** Parent GameObject and add a ``Slider`` component. Ensure the ``Interactable`` setting is unticked. Set ``Transition`` and ``Navigation`` to None. 
 
Step 8:

For ``Fill Rect``: Drag in the **Fill** gameObject previously made and set your direction of fill. Set your Maximum and minimum value as necessary.
 
Step 9: 

Under the original **Progress Bar** GameObject, create a Script named ``Progress Bar`` and copy in the following code:
 
     using System.Collections;
     using System.Collections.Generic;
     using UnityEngine;
     using UnityEngine.UI;

     [ExecuteInEditMode] //So you can test the progressBar without having to set the engine to Play
     public class progressbar : MonoBehaviour
     { 
         public int current;
         public Slider fill;


         // Start is called before the first frame update
         void Start()
         {

         }

         // Update is called once per frame
         void Update()
         {
             GetCurrentFill();
             current = //Here reference the script and int that your slider is monitoring as: script.intname
         }

         void GetCurrentFill()

         {
             float fillAmount = (float)current;
             fill.value = fillAmount;
         }

     }

Step 9:

 Save your script, set the Fill reference in the script as the **Progress Bar** gameObject  
