# Sumac

Sumac is a code smell detector for iOS  apps written in Objective-C and Swift.

Sumac extends the existing tool [Paprika](https://github.com/GeoffreyHecht/paprika), which so far only supports Android apps written with in Java.

For the moment, Sumac supports 3 iOS-specific code smells:
  * **Massive View Controller (MaVC)**: 
    Most of iOS apps are designed using MVC, a design/architectural pattern that splits the application into three layers model, view, and controller.
    In this pattern, the default role of a controller is to link the model and the view.
However, in iOS, app controllers tend to carry much more responsibilities than connecting the model to the views.
    They handle UI events, like clicks and swipes, since they are a part of the response chain and they also receive several system warnings.
    All these additional responsibilities make the controllers massive, complex, and difficult to maintain.
    
  * **Ignoring Low-Memory Warning (ILMW)**: 
  In iOS, when the system requires more memory to perform its tasks, it sends low-memory warnings to the apps holding an important memory space via the method *did-Receive-Memory-Warning:* of the *UIViewController* class.
  Every view controller should implement this method to free the unused memory space—*e.g.*, view elements that are not currently visible.
  When this method is not implemented, the view controller cannot react to the system warnings, and if the application is holding an important memory space, it can be killed by the system.
  
  * **Blocking The Main Thread (BTMT)**: 
  In iOS, the UIKit is directly tied to the main thread, so all the graphical user interface interactions are in this thread    and are impacted by the execution time of the other operations sharing it.
Hence, every heavy processing in the main thread makes the UI completely unresponsive.
The operations that often block the main thread are:
    * The synchronous access to the network,
    * The access to the disk, especially for reading or writing large files,
    * The execution of long tasks, like animations or complex data processing. 
    
Sumac also detects 4 well-known Object Oriented code smells:
  * **BLOB** a.k.a. God Class.
  * **Long Method**
  * **Complex Class**
  * **Swiss Army Knife**
  
For more details about Sumac and the detected code smells, please refer to this [research paper](https://hal.inria.fr/hal-01471294/document).


# Installation and Configuration
Coming soon.
  
