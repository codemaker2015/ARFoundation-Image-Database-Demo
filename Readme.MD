# Image Tracking with AR Foundation in Unity
 
One of the features of AR Foundation in Unity is Image Tracking. It’s one of the “oldest” methods to position virtual elements in the real world.
Is this still relevant today? Of course, it is! Markers are still helpful for the users because you can place them exactly where you want them to be. You can’t do this marker-less yet.
So, do you want to learn how to set up the project to use image tracking for AR?

### Setup project

As with other posts about AR (Face Tracking and Building AR Game), we have to start with the Package Manager and its packages for AR.
You will have to install the following packages: AR Foundation, ARCore XR Plugin (for Android support), and ARKit XR Plugin (for iOS support).

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot1.png "Screenshot")
##### AR packages in Package Manager.

Now we can start working.

### Creating Marker

The first thing we should do now is to set up the markers for our project.
To do that, go to the Project window and click Create > XR > Reference Image Library.

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot2.png "Screenshot")
##### Creating Reference Image Library.
Now you have to import an image which you want to use as a marker. Add it to the newly created ReferenceImageLibrary object.


![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot3.png "Screenshot")
##### Marker Image setup.

### Creating a Reference Image Library

In the Unity Editor, create a Reference Image Library, then fill it with reference images. In the Editor, click Assets > Create > XR > Reference Image Library:

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot4.png "Screenshot")
 
This creates a new reference image library asset in your project. Select it, and start adding reference images by clicking "Add Image" and populating the resulting fields:
  
Reference images have a name, optional size, and can optionally keep the texture at runtime.

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot3.gif "Screenshot")

I would also recommend specifying the real-life size of the marker. If you have a print of it, just measure it on the paper.

Note: Please use arcoreimg tool to check the quality of the image before creating the reference library.

For downloading arcoreimg tool [Click Here](https://raw.githubusercontent.com/google-ar/arcore-android-sdk/master/tools/arcoreimg/windows/arcoreimg.exe)

For usage [Click Here](https://developers.google.com/ar/develop/c/augmented-images/arcoreimg)

### Build AR scene 

With every AR scene, we have to start by adding AR Session and AR Session Origin to the scene.
You can do it by going to the Hierarchy window and clicking Create > XR > AR Session and Create > XR > AR Session Origin.

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot6.png "Screenshot")
##### Creating AR Session and AR Session Origin.

### Image Tracking

When you have both of them, you can add AR Tracked Image Manager to the AR Session Origin game object.
Of course, now we also have to assign the references in it. 

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot7.png "Screenshot")
##### AR Tracked Image Manager Component
One reference is for our ReferenceImageLibrary and the second one if for our prefab which will be displayed on the marker. Be aware that 1 unit in Unity space is 1 meter in the real world!
You can also specify how many images you want to track. The maximum number may vary between different devices so I would recommend checking it (read more).

### Build settings 

Depending on the platform you are using, you may want to change some build settings.
For Android, if your project requires AR support, you have to use at least API Level 24.

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot8.png "Screenshot")
##### Minimum API level for Android.

And for iOS, you will have to use at least iOS 11.0 and check “Require ARKit support“.

![Screenshot](https://github.com/codemaker2015/ARFoundation-Image-Database-Demo/blob/master/Screenshots/Screenshot9.png "Screenshot") 
##### Minimum iOS version.

