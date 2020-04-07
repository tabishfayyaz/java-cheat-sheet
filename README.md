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
`PriorityQueue<Integer> pq = new PriorityQueue<>((x, y) -> y - x);`

### convert priority queue (min-heap) to array list:
` new ArrayList<Integer>(minHeap);`


