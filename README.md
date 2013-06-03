Proxy pattern
========

In computer programming, the proxy pattern is a software design pattern.

A proxy, in its most general form, is a class functioning as an interface to something else. The proxy could interface to anything: a network connection, a large object in memory, a file, or some other resource that is expensive or impossible to duplicate.

A well-known example of the proxy pattern is a reference counting pointer object.

In situations where multiple copies of a complex object must exist, the proxy pattern can be adapted to incorporate the flyweight pattern in order to reduce the application's memory footprint. Typically, one instance of the complex object and multiple proxy objects are created, all of which contain a reference to the single original complex object. Any operations performed on the proxies are forwarded to the original object. Once all instances of the proxy are out of scope, the complex object's memory may be deallocated.


![Diagram: ] (http://umlsync.org/github?path=diagrams/classDiagram.umlsync "")

### Example

The following Java example illustrates the "virtual proxy" pattern. The ProxyImage class is used to access a remote method.

The example creates first an interface against which the pattern creates the classes. This interface contains only one method to display the image, called displayImage(), that has to be coded by all classes implementing it.

The proxy class ProxyImage is running on another system than the real image class itself and can represent the real image RealImage over there. The image information is accessed from the disk. Using the proxy pattern, the code of the ProxyImage avoids multiple loading of the image, accessing it from the other system in a memory-saving manner.

```
interface Image {
    public void displayImage();
}
 
//on System A 
class RealImage implements Image {
 
    private String filename = null;
    /**
     * Constructor
     * @param FILENAME
     */
    public RealImage(final String FILENAME) { 
        filename = FILENAME;
        loadImageFromDisk();
    }
 
    /**
     * Loads the image from the disk
     */
    private void loadImageFromDisk() {
        System.out.println("Loading   " + filename);
    }
 
    /**
     * Displays the image
     */
    public void displayImage() { 
        System.out.println("Displaying " + filename); 
    }
 
}
 
//on System B 
class ProxyImage implements Image {
 
    private RealImage image = null;
    private String filename = null;
    /**
     * Constructor
     * @param FILENAME
     */
    public ProxyImage(final String FILENAME) { 
        filename = FILENAME; 
    }
 
    /**
     * Displays the image
     */
    public void displayImage() {
        if (image == null) {
           image = new RealImage(filename);
        } 
        image.displayImage();
    }
 
}
 
class ProxyExample {
 
   /**
    * Test method
    */
   public static void main(String[] args) {
        final Image IMAGE1 = new ProxyImage("HiRes_10MB_Photo1");
        final Image IMAGE2 = new ProxyImage("HiRes_10MB_Photo2");     
 
        IMAGE1.displayImage(); // loading necessary
        IMAGE1.displayImage(); // loading unnecessary
        IMAGE2.displayImage(); // loading necessary
        IMAGE2.displayImage(); // loading unnecessary
        IMAGE1.displayImage(); // loading unnecessary
    }
 
}
```


![Diagram: ] (http://umlsync.org/github?path=diagrams/ElementInitialization.umlsync "")
