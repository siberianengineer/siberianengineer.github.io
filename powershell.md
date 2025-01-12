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

```
$files = Get-ChildItem "C:\MyFolder"
foreach ($file in $files) {
    Write-Host "File: $($file.Name)"
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






Here's the full code for your `index.md` file to create a PowerShell cheat sheet on GitHub Pages. This version includes a variety of common PowerShell commands, aliases, file operations, and system-related commands, formatted in Markdown for clarity.

```markdown
# PowerShell Cheat Sheet

A quick reference guide for common PowerShell commands. This cheat sheet will help you work more efficiently with PowerShell and understand some of the most commonly used cmdlets.

---

## Basic Commands

### 1. Get the current directory
```powershell
Get-Location
```

### 2. List files in the current directory
```powershell
Get-ChildItem
```

### 3. Change directory
```powershell
Set-Location 'C:\path\to\directory'
```

### 4. List processes
```powershell
Get-Process
```

### 5. Get system information
```powershell
Get-ComputerInfo
```

---

## File Operations

### 1. Copy a file
```powershell
Copy-Item 'C:\source.txt' 'C:\destination.txt'
```

### 2. Move a file
```powershell
Move-Item 'C:\source.txt' 'C:\destination.txt'
```

### 3. Remove a file
```powershell
Remove-Item 'C:\file.txt'
```

### 4. Rename a file
```powershell
Rename-Item 'C:\oldname.txt' 'C:\newname.txt'
```

### 5. Create a new directory
```powershell
New-Item 'C:\new_folder' -ItemType Directory
```

---

## System Information

### 1. Get a list of installed services
```powershell
Get-Service
```

### 2. Get hardware information
```powershell
Get-WmiObject Win32_ComputerSystem
```

### 3. Get disk space usage
```powershell
Get-PSDrive
```

### 4. Get the current user
```powershell
Get-CurrentUser
```

---

## Aliases

PowerShell has a variety of aliases to shorten commonly used cmdlets.

| Alias | Command            | Description                         |
|-------|--------------------|-------------------------------------|
| `ls`  | `Get-ChildItem`     | Lists files in the current directory |
| `cd`  | `Set-Location`      | Changes the current directory       |
| `ps`  | `Get-Process`       | Lists running processes             |
| `rm`  | `Remove-Item`       | Deletes a file or folder            |
| `cp`  | `Copy-Item`         | Copies a file or folder             |
| `mv`  | `Move-Item`         | Moves a file or folder              |

---

## Variables

### 1. Set a variable
```powershell
$myVar = "Hello, PowerShell!"
```

### 2. Get the value of a variable
```powershell
$myVar
```

---

## Piping and Redirection

### 1. Pipe output to another command
```powershell
Get-Process | Where-Object {$_.CPU -gt 100}
```

### 2. Redirect output to a file
```powershell
Get-Process > processes.txt
```

### 3. Append output to a file
```powershell
Get-Process >> processes.txt
```

---

## Loops

### 1. ForEach loop
```powershell
foreach ($file in Get-ChildItem) {
    Write-Host $file.Name
}
```

### 2. While loop
```powershell
$i = 0
while ($i -lt 5) {
    Write-Host "Iteration $i"
    $i++
}
```

---

## Conditional Statements

### 1. If-Else
```powershell
if ($a -gt $b) {
    Write-Host "$a is greater than $b"
} else {
    Write-Host "$a is less than or equal to $b"
}
```

### 2. Switch
```powershell
switch ($day) {
    "Monday" { Write-Host "Start of the week" }
    "Friday" { Write-Host "Almost weekend" }
    default { Write-Host "Just another day" }
}
```

---

## Remote Management

### 1. Run a command on a remote computer
```powershell
Invoke-Command -ComputerName 'RemotePC' -ScriptBlock { Get-Process }
```

### 2. Enter a remote PowerShell session
```powershell
Enter-PSSession -ComputerName 'RemotePC'
```

---

## Useful Shortcuts

| Shortcut         | Action                         |
|------------------|--------------------------------|
| `Ctrl + C`       | Stop the current command       |
| `Ctrl + L`       | Clear the screen               |
| `Tab`            | Auto-complete commands/paths   |
| `Up Arrow`       | Recall previous commands       |
| `F1`             | Display help for a command     |

---

## Additional Resources

- [PowerShell Documentation](https://docs.microsoft.com/en-us/powershell/)
- [PowerShell Community](https://github.com/PowerShell/PowerShell)

---

### Contributions
Feel free to contribute and suggest more commands to improve this cheat sheet. Open an issue or submit a pull request with your suggestions!

---

_This cheat sheet is regularly updated with more PowerShell commands and tips._
```

### Key Points in This Cheat Sheet:

- **Basic Commands**: Includes fundamental cmdlets like `Get-Location`, `Get-Process`, etc.
- **File Operations**: Provides common file handling commands such as `Copy-Item`, `Remove-Item`, etc.
- **System Information**: Useful commands for gathering system info (`Get-ComputerInfo`, `Get-Service`).
- **Aliases**: Common PowerShell aliases for convenience.
- **Variables**: Examples of how to declare and use variables.
- **Piping and Redirection**: Shows how to pipe commands and redirect outputs.
- **Loops**: Includes examples for `foreach` and `while` loops.
- **Conditional Statements**: `if-else` and `switch` examples for decision-making.
- **Remote Management**: Examples for managing remote systems using `Invoke-Command` and `Enter-PSSession`.
- **Shortcuts**: Useful keyboard shortcuts for improving your workflow.

### Next Steps:
1. Copy this code into your `index.md` file.
2. Push it to your GitHub repository.
3. Visit your GitHub Pages URL to see the cheat sheet in action.

This should give your users a neat and organized PowerShell cheat sheet! Feel free to expand and customize it further as you add more commands.