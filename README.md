# Single for-loop traversal over 2D arrays

It demonstrates the use of a single for-loop for two-dimensional arrays. It shows the traversal of a two-dimensional array by one for-loop structure. A 2D-array variable (<i>A</i>) is declared with mixed datatypes as before, namely with string literals and number literals. A string variable <i>t</i> is initially set to empty. A variable <i>v</i> is set to zero and it represents the main counter of the for-loop. Another two variables (ie. <i>i</i> and <i>j</i>) are initialized with value zero and are the main coordinates for element identification. Each dimension of array <i>A</i> is stored in variables <i>n</i> and <i>m</i>, namely the number of rows in n and the number of columns in <i>m</i>. The upper limit of the for-loop is calculated based on the two known dimensions <i>n</i> and <i>m</i>. Thus, <i>m</i> times <i>n</i> establishes the upper limit of the for-loop. Here, the value of the counter <i>v</i> from the for-loop is used to calculate the <i>i</i> and <i>j</i> values that are used as an index to traverse the array variable <i>A</i>. The value of variable <i>j</i> is computed as the <i>v % m</i> and the result of this expression indicates the reminder (ex. 5 mod 3 is 2). The secret to this implementation is a condition that increments a variable <i>i</i> (rows) each time <i>j</i> (columns) equals zero. Thus, in this manner this approach provides the <i>i</i> and <i>j</i> values that a nested for-loop provides. At each iteration, the value from an element is added to the content of variable <i>t</i>. Once the end of the for-loop is reached, the value collected in variable <i>t</i> is printed in the output for inspection.

# C#
```C#
using System;
class HelloWorld {
  static void Main() {
    
    string[, ] A = new string[, ] {
                                    {"a","b"},
                                    {"c","d"},
                                    {"e","f"},
                                    {"g","h"}
                                  };
    string t = "";
    
    int n = A.GetLength(0);
    int m = A.GetLength(1);
    int i = 0;
    int j = 0;

    for (int v = 0; v < n*m; v++) {
        
        j = v % m;
        if(v!=0 && j == 0){i++;}
        
        t += v + " A["+i+","+j+"]=";
        t += A[i,j] + "\n";
    }

    Console.WriteLine(t);
  }
}
```

# C++
```c++
#include <iostream>
using namespace std;

int main()
{
    string A[][2] = {
                    {"a","b"},
                    {"c","d"},
                    {"e","f"},
                    {"g","h"},
                    };
    string t = "";
    
    int n =  sizeof(A) / sizeof A[0];
    int m = sizeof A[0] / sizeof(string);

    int i = 0;
    int j = 0;

    for (int v = 0; v < n*m; v++) {
        
        j = v % m;
        if(v!=0 && j == 0){i++;}
        
        t += to_string(v);
        t += " A["+to_string(i)+"][";
        t += to_string(j)+"]=";
        t += A[i][j] + "\n";
    }
    cout<<t;

    return 0;
}
```

# Java
```java
public class Main
{
    public static void main(String[] args) {

        String[][] A = new String[][] {
                                    {"a","b"},
                                    {"c","d"},
                                    {"e","f"},
                                    {"g","h"}
                                    };
    
        String t = "";
        
        int n = A.length;
        int m = A[0].length;
    
        int i = 0;
        int j = 0;
    
        for (int v = 0; v < n*m; v++) {
            
            j = v % m;
            if(v!=0 && j == 0){i++;}
            
            t += v + " A["+i+","+j+"]=";
            t += A[i][j] + "\n";
        }
        
        System.out.println(t);
    }
}
```

# Javascript
```js
var A = [
   ["a", 88, 146],
   ["b", 34, 124],
   ["c", 96, 564],
   [100, 12, "d"],
        ];

let t = "";
let n = A. length;    // rows
let m = A[0].length;  // columns

let i = 0;
let j = 0;

for (let v = 0; v < n*m; v++) {
   
   j = v % m;
   
   if(v!=0 && j == 0){i++;}
   
   t += v + " A["+i+"]["+j+"]=";
   t += A[i][j] + "\n";
}

print(t);
```

# PHP
```php
<?php

    $A = [
       ["a", 88, 146],
       ["b", 34, 124],
       ["c", 96, 564],
       [100, 12, "d"],
         ];
    
    $t = "";
    $n = count($A);
    $m = count($A[0]);
    
    $i = 0;
    $j = 0;
    
    for ($v = 0; $v < $n*$m; $v++) 
    {
        $j = $v % $m;
       
        if($v!=0 && $j == 0){$i++;}
    
        $t .= $v . " A[".$i."][".$j."]=";
        $t .= $A[$i][$j] . "\n";
    }
    
    echo $t;

?>
```

# Perl
```perl

my @A = (
    ["a", 88, 146],
    ["b", 34, 124],
    ["c", 96, 564],
    [100, 12, "d"],
        );

my $t = "";
my $n = $#A + 1;       # rows
my $m = $#{$A[0]} + 1; # columns

my $i = 0;
my $j = 0;

for ($v = 0; $v < $n*$m; $v++) {
 
    $j = $v % $m;
   
    if($v != 0 && $j == 0){$i++;}

    $t .= $v . " A[".$i."][".$j."]=";
    $t .= $A[$i][$j] . "\n";
}

print $t;
```

# Python
```python

A = [["a", 88, 146],
     ["b", 34, 124],
     ["c", 96, 564],
     [100, 12, "d"]]

t = ""
n = len(A)     # rows
m = len(A[0])  # columns

i = 0
j = 0

for v in range(0, n*m):
    j = v % m
    if(v != 0 and j == 0):
        i = i + 1
    t += str(v) + " A[" + str(i) + "]["
    t += str(j) + "]=" + str(A[i][j]) + "\n"

print(t)
```

# Ruby
```ruby
A = [
    ["a", 88, 146],
    ["b", 34, 124],
    ["c", 96, 564],
    [100, 12, "d"],
    ]

t = ""
n = (A.size)     # rows
m = (A[0].size)  # columns

i = 0
j = 0

for v in 0..(n*m)-1

    j = v % m

    if(v != 0 and j == 0)
        i = i + 1
    end
    
    t += v.to_s + " A[" + i.to_s + "]["
    t += j.to_s + "]=" + A[i][j].to_s + "\n"
end

puts(t)
```

# VB
```vb
Sub main()

    Dim A(0 To 1, 0 To 2) As String
    Dim i As Integer
    Dim t As String

    A(0, 0) = "a"
    A(0, 1) = "b"
    A(0, 2) = "c"
    A(1, 0) = "d"
    A(1, 1) = "e"
    A(1, 2) = "f"
    
    ' rows
    n = UBound(A, 1) - LBound(A, 1) + 1
    ' columns
    m = UBound(A, 2) - LBound(A, 2) + 1
    
    i = 0
    j = 0
    
    For v = 0 To (n * m) - 1
    
        j = v Mod m

        If (v <> 0 And j = 0) Then i = i + 1
        
        t = t & v & " A(" & i & "," & j & ")="
        t = t & A(i, j) & vbCrLf

    Next v
    
    Debug.Print (t)

End Sub
```

# References

- Paul A. Gagniuc. <i>An Introduction to Programming Languages: Simultaneous Learning in Multiple Coding Environments</i>. Synthesis Lectures on Computer Science. Springer International Publishing, 2023, pp. 1-280.
