Learning Journal

29/09/2020

  Set up a github and repository to make the learning journal

13/10/2020
  
  Started planning my first tutorial: a changing progress bar (akin to a health bar but not) that both rose and fell. Found a tutorial on making general progress bars using unity.

14/10/2020
   
   Using multiple tutorials as reference, I tried my first attempt at making a progress bar using code from my IPP 2d game project as a guide. I had some issues at the moment
   as the mask code doesn't seem to want to work when I test it despite the code not having errors and no issues coming up in the console. Currently Troubleshooting to see what    the issue could be.
   
18/10/20
    
   After doublechecking my code, I realised I didn't use ``[ExecuteInEditMode]`` so when I went to test it, it wouldn't work. Once I edited the Progress Bar script, it worked      perfectly. Despite this, there are still issues regarding the stretching of the sprite that causes distortion. From here I will ask someone to test out my tutorial to see if
   they have this issue.

20/10/20
 
  Currently having my tutorial 1 tested, starting info gathering for next tutorial
  
24/10/20

  Tutorial 1 still being tested, decided to make my 2nd tutorial on raycasting button prompt. Raycast currently works, but having issues on getting the gameobject/ui to
  activate/deactivate when raycast is hit/unhit. Will stop here and take a few days break.
  
27/10/20

  Got my prompt script working, and will now commence writing up the tutorial and have that tested. Tutorial 1 is *still* being tested, I will likely have to find someone else
  to test it for me. From here I will begin to look for information for my 3rd tutorial, still unsure as to what that will be.
  
30/10/20

  Decided to make my 3rd tutorial on 1st person player/camera movement that doesn't involve mouse input. Still gathering information on that since the script offered by unity
  has a lot of sections that seem redundant in my case, and videos are fairly confusing and long winded. 
  
1/11/20

  Figured out my script for my player control movement, currently typing up my 3rd tutorial and will migrate my 2nd tutorial into github shortly.
 
3/11/20

  Started and completed my 4th tutorial: an inventory UI system. Will begin combining the 4 scripts I have next week, starting with the Rayhit button prompt and the player movement. Will begin typing up my 4th tutorial soon as I only have it on paper.
  
10/11/20

  Connected my rayhit and player movement scripts as wanted, however I had a bug where the ray wouldn't rotate with the player. Visually the debug ray rotated but in terms of code it wouldn't activate the button prompt unless the player model was at a specific angle. Fixed this by changing Vector3.Forward to Transform.Forward. Will need to go back to my old tutorial and change this so users don't have this issue.
  
17/11/20

  Tried to connect the ray button prompt and the progress bar using a counter, however I had some minor issues referencing to another script. Realised the issue was that I wasn't setting the int variable 'CollectTotal' in the Rayhit script as a static variable. As a result it wasn't referencing properly. Now done and the script is working.
  
24/11/20
