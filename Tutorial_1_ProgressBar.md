Step 1:
 Open a new unity project
  
Step 2: 
 Right click the ``Heirarchy tab``, go down to ``UI`` and select ``Canvas``
  
Step 3:
 Right click the Heirarchy tab again and under the UI section, select ``Image``, which will automatically set itself as a child of the Canvas. From here shape the rectangle as
 you like, however, this tutorial is for a linear progress bar so it is best to keep it in a rectangular form. This will be the ``Parent component`` of the progress bar so rename
 it as you like, from here on in I will refer to it as ``Parent Bar``.
 
Step 4:
 Right click the **Parent Bar** in the Heirarchy Tab and create a new ``UI>Image`` (henceforeward reffered to as ``Mask``) and set both UI>Images to whatever bar 
 sprite you would like.
  
Step 5:
 In the Inspector under the Rect Transform, click the Anchor Select. Hold Alt down, go down to the 'Stretch' section and select the option ``Fill to Parent``. Set the
 image type to 'Filled' in the image component.
 
Step 6:

 Duplicate the child (henceforeward referred to as ``Fill``) and make it a child of **Mask**. In the Image component, set the image type back to ``Sliced``. Ensure that the Anchor
 Preset is still set to **Fill to Parent**.

Step 7:

 Select **Mask** from the Heirarchy and changed the fill method to Horizontal, add a ``Mask Component`` and turn off the ``Show Mask Graphic``
 
Step 8:
 
 Under the original **Parent Bar** GameObject reate a Script named ``Progress Bar`` and copy in the following code:
 
    using System.Collections;
    using System.Collections.Generic;
    using UnityEngine;
    using UnityEngine.UI;
    
    [ExecuteinEditMode] //To ensure the script works prior to loading the game up in Play Mode

    public class ProgressBar : MonoBehaviour
    {
        public int maximum;
        public int current;
        public Image Mask;

        // Start is called before the first frame update
        void Start()
        {

        }

        // Update is called once per frame
        void Update()
        {
            GetCurrentFill();
        }

        void GetCurrentFill()

            {
                float fillAmount = (float)current / (float)maximum;
                Mask.fillAmount = fillAmount;
            }

    }

Step 9:

 Save your script, set your **Mask** GameObject as the public 'Mask' in the script component. Input your maximum and current values for the progress bar and you are done. 
