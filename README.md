
### common operations
```
// HashSet  =>  HashSet<Integer> hSet = new HashSet<>();
// HashMap   =>  HashMap<Integer,String> hMap = new HashMap<>();  
// HashTable =>  Hashtable<Integer,String> hTable = new Hashtable<>();  
// Hash Set Functions => {add(), remove(), contains()}
// Map Interface Functions => {put(key,value), putIfAbsent(key,value), get(key), getOrDefault(key, defaultValue), containsKey(key), containsValue(value), remove(key)}
// Queue => {boolean add(E value), E remove(), E element()} -> throws exception, {boolean offer(E value), E poll(), E peek()} -> return special value or null
// Deque => {addFirst/Last(E value), E removeFirst/Last, E getFirst/Last()} -> throws exception {boolean offerFirst/Last(E value), pollFirst/Last(), peekFirst/Last()} -> return special value or null
// for Deque -> first=beginning=head-of-queue and last=ending=tail-of-queue (if you visualize this head & tail is not reference to a linked list terminology but in fact reverse)
// Stack => {E push(E value), E pop(), E peek()} -> throws exception if stack is empty
```

### Declare a Stack
`Stack<Integer> stack = new Stack<Integer>();`

### Declare a Queue
`Queue<Integer> queue = new LinkedList<Integer>();`

### common constants, methods
```
int min = Integer.MIN_VALUE // 2^31-1
int max = Integer.MAX_VALUE //-2^31
Math.max()
Math.min()
```

### print/access each character of a string
```
for (char chr : "abcdef".toCharArray())
      System.out.println(chr);
```

### Initialize String from char array
```
String newWord = new String("abcdef".toCharArray());
```

### print/access each number of an integer array
```
for (int num : result)
      System.out.print(num + " ");
    System.out.println();
```

### declare a generic Pair class
```
class Pair<T> {
    T first;
    T second;

    Pair(T first, T second){
        this.first = first;
        this.second = second;
    }
}
```


### ways to declare and initialize an array
```
//Declaration Syntax
int myArray1[]; 
int[] myArray2; 

//Initialization Syntax
int[] myArray1 = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
int[] myArray2;

myArray2 = new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

### declare and initialize 2D array
```
class TwoDArray {
    public static void main( String args[] ) {
    
      int rows = 3;
      int columns = 4;
      
      int [][] my2DArray;
      my2DArray = new int[rows][columns];  
    }
}
```

### declare and initialize 2D array with unknown number of columns
```
class TwoDArray {
  public static void main( String args[] ) {
  
    int[][] myArray = new int[10][] ;
    for (int i = 0; i < 10; i++)
    {  
      myArray[i] = new int [10];
      for (int j = 0; j < 10; j++){
        myArray[i][j] = i + j;     
        System.out.println(myArray[i][j]);  
      }
    }
  }
}
```
### declare and initialize a 2D array with default values
```
int rows = 3;
int columns = 4;
int[][] array = new int[rows][columns];

for (int i=0; i<rows; ++i){
    Arrays.fill(array[i], -1);
}	
//OR	
for (int[] row : array){
    Arrays.fill(row, -2);
}
```

### iterate a HashMap using foreach:
```
Map<String, String> map = new HashMap<>();
map.forEach((key, value) -> System.out.println("[Key] : " + key + " [Value] : " + value));
```

### iterate a HashMap using entrySet:
```
Map<String, String> map = new HashMap<>();
	
for (Map.Entry<String, String> entry : map.entrySet()) {
	System.out.println("[Key] : " + entry.getKey() + " [Value] : " + entry.getValue());
}
```

### iterate a HashMap using iterator:
```
Map<String, String> map = new HashMap<>();
       
Iterator iter = map.entrySet().iterator();
while (iter.hasNext()) {
	Map.Entry entry = (Map.Entry) iter.next();
	System.out.println("[Key] : " + entry.getKey() + " [Value] : " + entry.getValue());
}
```

### different ways to iterate HashSet
```
HashSet<String> dictionary = getDictionary();

//1.
Iterator<String> it = dictionary.iterator();
while (it.hasNext()) {
	System.out.println(it.next());
}

//2.
dictionary.forEach(key -> {
	System.out.println(key);
});
            
//3.
for (String key : dictionary){
	System.out.println(key);
}
```

### iterate a Queue/Priority-Queue/Stack using iterator:
```       
Iterator<Integer> iter = queue.iterator();
while (iter.hasNext()) {
	Integer value = iter.next();
}
```


### priorityQueue in reverse order (max-heap):
`PriorityQueue<Integer> maxHeap = new PriorityQueue<>((x, y) -> y - x);`

`PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());`

### convert priority queue (max-heap) to array list:
` return new ArrayList<Integer>(maxHeap);`

### sort an Array in ascending order
`Arrays.sort(arr);`

### convert set of values into List
`Arrays.asList(...)`

### get substring from a String
```
str.substring(startIndex)		//till end of string
str.substring(startIndex, endIndex)	//endIndex is exclusive
```

### Build String with StringBuilder
```
StringBuilder builder = new StringBuilder();
builder.append('a');
builder.append('b');
builder.append("c");
System.out.println(builder.toString());
```

### Comparable interface
```
public class CustomClass implements Comparable<CustomClass> {
  
    // returns -1 if object is less than other, returns 0 if they're equal, and returns 1 otherwise
    @Override
    public int compareTo(CustomClass other) {
        return Integer.compare(getConfirmationNo(), other.getConfirmationNo());
    }
}
```

### Comparator interace - allows for multiple comparison logic and can plug in as lambda too
```
public class PlayerRankingComparator implements Comparator<Player> {
    @Override
    public int compare(Player firstPlayer, Player secondPlayer) {
       return Integer.compare(firstPlayer.getRanking(), secondPlayer.getRanking());
    }
}

public class PlayerAgeComparator implements Comparator<Player> {
    @Override
    public int compare(Player firstPlayer, Player secondPlayer) {
       return Integer.compare(firstPlayer.getAge(), secondPlayer.getAge());
    }
}

Comparator byRanking = (Player player1, Player player2) -> Integer.compare(player1.getRanking(), player2.getRanking());

Collections.sort(objects, PlayerRankingComparator);
Collections.sort(objects, PlayerAgeComparator);
Collections.sort(objects, byRanking);

```

### Random number between a range
`new Random().nextInt(end - start + 1) + start`


## Notes

**What is Java**
 * Object Oriented programming language
 * Portable - write once run anywhere (was not possible in the programming world when java was invented)
 * Very popular today in server-side applications

**What are the characteristics of Java (goals of the creator)**
 1. Simple, object-oriented, and familiar (at that time C & C++ were ruling)
 2. Robust and secure (JVM makes it difficult for direct access to machine level so that kind of makes it a bit more secure)
 3. Architecture-neutral and portable (does not care about underlying hardware architecturee because of JVM)
 4. High performance (these days JVM implementation have improved so much that it runs as fast as C or C++ programs)
 5. Interpreted, threaded and dynamic (bytecode is interpreted by JVM, some aspects of Java are dynamic, some are static but Java is very much dynamic) 

**What is JRE**
 * software used for running Java applications
 * stands for Java Runtime Environment
 * It is a set of software elemtns (Class loader, JVM, Libraries and utilities which assist the code to execute) that together run a Java application on a machine, little different from traditional model where you get an executable and you just run it like in C/C++
 * The JRE orchestrates activities between these software elements, it is the runtime environment where the Java code runs
 * Installed on machines that need to run Java applications


**What is JVM**
 * abstract virutal machine that the JRE spins up to run Java applications in
 * It's the runtime VM in which a Java program is run (an extra layer on top of your hardware)
 * Takes the compiled Java bytecode and runs it (input to the JVM is bytecode)
 * Has a specification that outlines how it should work (different implementation available)
 * Essential in making Java platform agnostic


**What is JDK**
 * software used for building Java applications
 * stands for Java Development Kit
 * It is a set of tools to help developers write Java programs (if you just want to execute java code you need JRE) but to write and publish you need JDK
 * Comes with the JRE (because you need to run what you develop)
 * Based off the Java language specification (two important specifications: one is for how JVM behaves the other is how JDK behaves)
   * if you write a certain line of java code this is what should happen or this is what error should occur (this is in specification)
   * there are multiple JDK but as long as it is certified it'll follow the specification and result in bytecode that you intended to write
 * Includes (java compiler which converts java code into bytecode, class libraries which is core native API of java, utilities like packaging into a jar)

**What is Java byte code**
 * Instruction set for JVM
 * Generated by the process of compilation of a Java program
 * JVM takes this and executes it
 * Cannot be run natively on a machine
 * Bytecode is consistent across machines
   * This enables the "write-once-run-anywhere" feature of Java

**What is the difference between path and classpath**
 * Both are environment variables
 * PATH is an operating system specific variable that influences what binaries are available for running (this has nothing to do with Java but any executable you want access across the command promot)
 * CLASSPATH (the path to the classes for compilation/execution) is a Java construct to indicate where all the compiled classes and jars are available. This could be multiple locations

**What is the difference between sourcepath and classpath**
 * Sourcepath is where the classes reside (that you write and compile) e.g. your IDE might have SRC directory. It indicates to the compiler this is where your source code is
 * Classpath is where your dependencies - libraries/jars go
 * Compiler and Runtime scan all the different paths in CLASSPATH for bytecode and classes

**What are the different memory areas allocated by the JVM**
 * Heap
   * Space where JVM allocates memory for objects
   * Kind of "Global" space
   * Largest of the memory space
 * Stack
   * Holds thread level data
   * Local variables and object references (but remember these references point to the heap)
   * Call frames for each method execution
   * Kind of short lived
 * Code area (meta space)
   * Stores bytecode, JIT info
 * Implementation/native area
   * Registers
   * C implementation stacks 

**What is difference between permgen and metaspace**
 * Memory areas in the JVM
 * Before Java 8, there was a memory area called PermGen (permanent generation memory)
 * Java 8 onwards, this is called Metaspace
 * PermGen is gone
 * PermGen had a fixed max size allocated (configurable)
 * Metaspace expands as needed by default
 * Has maxMetaSpaceSize configuration. Triggers garbage collection when hit
 * Because of class loading/unloading, no "permanent generation" anymore
 * The way things grow is different: PermGen had a hard limit but Metaspace it's managed as JVM feels like, things go in and out

**What is garbage collection**
 * Process of removing unused and orphaned objects from the heap
 * Automatic process. Does not need programmer intervention
 * Has APIs to trigger programmatically (not recommended)
 * Generation based approach (things that are new have a stronger likelihood of being deallocated, things that have been around for a while have a stronger likelihood of staying around for a while)
 * Benefit: no manual memory management
 * Drawback: performance intrusion (small impact when garbage collection is running parallel to your own execution, fraction of a fraction of second)

**What is JIT compilation**
 * Java code is executed as bytecode as oppose to native code
 * JVM selectively converts certain bytecode instructions to native code (depending upon how JVM perceives code usage e.g. a 50K iterations loop)
 * Converts to the native instruction set of the CPU it is being run on
 * Makes a judgement call based on usage, performance chractertistics
 * Hence "Just In Time"

**How and why do you configure heap space in Java**
 * Configured using flags passed to JVM: -Xms (initial memory allocation pool) and -Xmx (maximum allocation, you generally tweak if it too much GC is happening)
 * When maximum is hit, JVM does:
  * Garbage collection
  * Out of memory errors (if not enough objects to recover)
 * You don't want space to be too little (would result in too much garbage collection or you'll run out of memory)
 * You don't want space to be too much (your application is taking up too much space from others) 

**How and why do you configure stack size in Java**
 * Configured using flag -Xss (initial stack size)
 * Stack grows dynamically
 * When all available memory is consumed:
   * Stack overflow exception
   * Usually not a big deal
   * Stack overflow usually because of circular invocation

**What is a classloader**
 * Classes (bytecode) is loaded into memory during execution
 * Part of JRE
 * They load Java classes into the runtime to make it available for the JVM
 * This happens only when needed and if the class is already not available in memory:
   * JVM requests a class
   * Class loader tries to find it in CLASSPATH and load it into metaspace

**What are the different types of classloaders**
 * Application/System class loader
   * Classes in your CLASSPATH (classes you have written, library you are using etc.)
 * Extension class loader
   * Core Java JDK classes
 * Bootstrap class loader
   * Loads the other class loaders
   * Core Java runtime classes (these are some low level stuff)
 * Custom class loaders (you can write your own)      

**What is public static void main**
  * *public static void* are modifiers to a method called *main*
  * public: method is accessible outside the class
  * static: a class instance isn't needed
  * void: method doesn't return anything
  * main: special name convention to indicate an execution entry point
  * order of modifiers don't matter: *static void public main* works just as well, modifiers must be before the method  

**Can you run code before the main method starts**
 * Yes, you can run code before main method starts
 * This can be done by using static blocks `static{}`
 * There can be multiple static initialization blocks
 * Static blocks in a class execute when the class is loaded
 * So, this runs before the main method is executed (for the main method to run Java has to load the class first)

**Difference between break and continue**
 * Both are used in loops
 * Break is used to end the loop immediately (e.g. looping an array until you find an exceptional case)
 * Continue is used to end that particular iteration (e.g. processing every element but skipping some on some condition)
 * break is also used in switch (to prevent fall through)

**Difference between float and double**
 * Both are real numbers e.g. 22/7 (whole numbers are precise were has 22/7 might need infinite precision)
 * Both are imprecise so you really can't compare them for equality as they might have a difference at 100th/200th decimal place (might need infinite precision/decimal-places)
 * Float takes 32 bit. Double takes 64 bit (double is literally double the size of float)
 * Double has more precision than float
 * By default, floating point numbers are double e.g. `var a = 3.14` is Double by default (var is Java 10 feature)
 * Use float mostly for space optimizations but recommendation is to use Double
 * A double can be cast to a float (with possible precision loss)

**What are the primitive types in Java**
 * byte: 8 bit signed twos compliment
 * char: 16 bit Unicode
 * short: 16 bit signed twos compliment
 * int: 32 bit signed twos compliment
 * long: 64 bit twos compliment (signed or unsigned)
 * float: 32 bit floating point
 * double: 64 bit floating point
 * boolean: One bit of information, size unspecified

**What is the default value of the local variables**
 * The local variables do not have default values (there is no gaurantee of value). They need to be initialized by the programmer otherwise compiler will complain 
 * These local variables could be primitives or object references

**Can a double be cast to a byte?**
 * Yes, a higher precision numeric type can be cast to a lower precision numberic type (any combination of data types)
 * This needs explicity casting `byte b = (byte)d`
 * Possible loss of data (loss conversion), you might end up getting different value  

**Can a byte be cast into a double**
 * A byte does not need to be cast into double. It can be automatically assigned
 * This is called implicit casting as no explicity casting is required, you are going from a smaller jug to a bigger jug
 * No possibility of data loss

**How do you break from a nested loop**
 * break keyword with labels: `label-name: while(){}`
 * Different from goto
 * When the break statement is encountered with the label/name of the loop, it skips the execution any statement after it and takes the control right out of this labelled loop
 * this could be nested deep any levels

**What are the different access modifiers in Java**
 * private: within the class only
 * package private: within the package only (default)
 * protected: by the classes of the same package, or by a sub-class of this class
 * public: can be accessed by all

## Links

- https://stackoverflow.com/questions/40471/what-are-the-differences-between-a-hashmap-and-a-hashtable-in-java
