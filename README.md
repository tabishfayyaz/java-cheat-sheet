
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


### Links

- https://stackoverflow.com/questions/40471/what-are-the-differences-between-a-hashmap-and-a-hashtable-in-java
