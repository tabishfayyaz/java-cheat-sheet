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
