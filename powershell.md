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