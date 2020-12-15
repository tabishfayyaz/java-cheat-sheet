
### common operations
```
// HashSet  =>  HashSet<Integer> hSet = new HashSet<>();
// HashMap   =>  HashMap<Integer,String> hMap = new HashMap<>();  
// HashTable =>  Hashtable<Integer,String> hTable = new Hashtable<>();  
// Hash Set Functions => {add(), remove(), contains()}
// Map Interface Functions => {put(key,value), putIfAbsent(key,value), get(key), remove(key), containsKey(key), containsValue(value), getOrDefault(key, defaultValue)}
// Queue => {boolean add(value), E remove, E element} -> throws exception, {boolean offer(value), E poll(), E peek()} -> return special value or null
```

### print/access each character of a string
```
for (char chr : "abcdef".toCharArray())
      System.out.println(chr);
```

### print/access each number of an integer array
```
for (int num : result)
      System.out.print(num + " ");
    System.out.println();
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

### priorityQueue in reverse order (max-heap):
`PriorityQueue<Integer> maxHeap = new PriorityQueue<>((x, y) -> y - x);`

### convert priority queue (max-heap) to array list:
` return new ArrayList<Integer>(maxHeap);`

### sort an Array in ascending order
`Arrays.sort(arr);`

### Convert set of values into List
`Arrays.asList(...)`

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
