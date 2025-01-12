# POWERSHELL


### Check the script execution
`Get-ExecutionPolicy`

### FOREACH Loop
```
$letterArray = 'a','b','c','d'
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

### Nested FOR Loop
```
for ($i = 1; $i -le 10; $i++) {
    for ($j = 1; $j -le 10; $j++) {
        $result = $i * $j
        Write-Host "$i multiplied by $j equals $result"
    }
}
```


```
# Outer loop: Iterate over numbers 1 to 3
for ($i = 1; $i -le 3; $i++) {
    # Inner loop: Multiply the current number with 1 to 3
    for ($j = 1; $j -le 3; $j++) {
        Write-Host -NoNewline "$($i * $j) "`t  # Print the product with a tab space
    }
    Write-Host ""  # New line after each row
}

```



Visualizing nested loops can really help you understand how they operate, especially when you're dealing with hierarchical or grid-like data. A nested loop is like having a loop inside another loop, and each loop works on a different level of a problem. 

### Visualizing with an Example: Multiplication Table

Let's start with a simple **multiplication table** example to show how nested loops work. This is a great way to visualize the process of iterating through each element.

#### Example Code:

```powershell
# Outer loop: Iterate over numbers 1 to 3
for ($i = 1; $i -le 3; $i++) {
    # Inner loop: Multiply the current number with 1 to 3
    for ($j = 1; $j -le 3; $j++) {
        Write-Host -NoNewline "$($i * $j) "`t  # Print the product with a tab space
    }
    Write-Host ""  # New line after each row
}
```

### Visual Representation:

Think of this as a **grid** of numbers, where the outer loop (`$i`) controls the rows, and the inner loop (`$j`) controls the columns.

```
i = 1  -> [1*1, 1*2, 1*3] -> [1, 2, 3]
i = 2  -> [2*1, 2*2, 2*3] -> [2, 4, 6]
i = 3  -> [3*1, 3*2, 3*3] -> [3, 6, 9]
```

### Breakdown:

1. **Outer loop** (`i = 1 to 3`):
    - Iterates through each row (1 to 3).
2. **Inner loop** (`j = 1 to 3`):
    - For each row, the inner loop runs and calculates the product of `i * j` for each column (1 to 3).

After each iteration of the inner loop, we print the result for that specific row (`i`) and column (`j`). The inner loop finishes completely for one row before moving to the next row.

So, the visualization helps show that the outer loop (`i`) runs completely first, and within each of those iterations, the inner loop (`j`) runs completely. The result is a matrix-like structure where the products of `i * j` are calculated.

### Another Visualization: 2D Grid (Processing Multidimensional Arrays)

Consider a **2D array** (or grid) of values. Let's visualize how a nested loop operates when we have a grid of data.

#### Example Code:

```powershell
# 2D Array (3x3 grid)
$grid = @(
    @(1, 2, 3),
    @(4, 5, 6),
    @(7, 8, 9)
)

# Outer loop iterates through rows (i)
for ($i = 0; $i -lt $grid.Length; $i++) {
    # Inner loop iterates through columns (j)
    for ($j = 0; $j -lt $grid[$i].Length; $j++) {
        Write-Host "Element at [$i, $j]: $($grid[$i][$j])"
    }
}
```

### Visual Representation:

Here's how you can visualize it:

```
  i \ j    0   1   2
       ---------------
    0   |  1   2   3
    1   |  4   5   6
    2   |  7   8   9
```

- The **outer loop** (`i`) iterates through the rows (0, 1, 2).
- The **inner loop** (`j`) iterates through the columns in each row.

For example:
1. **When i = 0 (row 0)**, the inner loop iterates over the columns (j = 0 to 2):
    - It prints the elements `grid[0][0]`, `grid[0][1]`, and `grid[0][2]`.
2. **When i = 1 (row 1)**, the inner loop again iterates over the columns:
    - It prints `grid[1][0]`, `grid[1][1]`, and `grid[1][2]`.
3. The same happens for **i = 2 (row 2)**.

### Flowchart Representation:

To further break down how nested loops work, a flowchart can be very useful. Here's a simple one to show how a nested loop for processing a 2D array would look:

```
Start
  |
  v
Outer loop (i = 0 to 2) 
  |
  v
Inner loop (j = 0 to 2)
  |
  v
Print grid[i][j] (e.g., grid[0][0])
  |
  v
Inner loop finishes for j = 2
  |
  v
Outer loop increments (i++)
  |
  v
Repeat until outer loop finishes
  |
  v
End
```

The outer loop controls how many rows we process, and for each row, the inner loop processes each element of that row.

### Using a **2D Grid** to Visualize the Flow:

A simple **2D grid** can help you understand how nested loops work:

1. Imagine each row represents one iteration of the outer loop.
2. Each column represents an iteration of the inner loop.
3. The entire grid is filled out as the inner loop processes each element of a row.

For example, in a 3x3 grid, you'd have:

```
Row 0 -> [1, 2, 3]
Row 1 -> [4, 5, 6]
Row 2 -> [7, 8, 9]
```

When you execute the code, **the outer loop iterates row by row**, and the **inner loop works through the columns in each row**.

### Visualizing with a Real-World Analogy: **Library Bookshelf**

Think of the process like a **library bookshelf**:
- The **outer loop** is the bookshelf, which has multiple shelves (rows).
- The **inner loop** is you, checking each book on the shelf (column) one by one.

1. You walk to the first shelf (outer loop iteration).
2. On that shelf, you check each book (inner loop iteration).
3. Once you finish checking all the books on the first shelf, you move to the next shelf (next iteration of outer loop).
4. You repeat the process until you’ve checked all the shelves and books.

---

### Key Takeaways:
- **Outer loop**: Controls the primary dimension (like rows, categories, or outer groups).
- **Inner loop**: Works on the secondary dimension (like columns, items in a category, or inner group).
- Visualization helps break down the flow into manageable pieces by looking at how data is iterated across multiple dimensions or groups.

By visualizing nested loops in this way—whether as a table, grid, or real-world analogy—you can better understand how each loop works independently and together.