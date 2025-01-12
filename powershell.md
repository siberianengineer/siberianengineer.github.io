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