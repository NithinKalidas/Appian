Print * from 1 to 5 in ascending order:

```javascript
a!localVariables(
  local!data: 5,
  a!forEach(
    enumerate(local!data),
    joinarray(repeat(fv!index, "*"), "")
  )
)
```

```
*
**
***
****
*****
```
```
a!localVariables(
  local!data: 5,
  a!forEach(
    enumerate(local!data),
    joinarray(repeat(local!data - fv!index + 1, "*"), "")
  )
)

*****
****
***
**
*
```
```
/*Palindrome */
a!localVariables(
  local!data: "Malayalam",
  if(
    joinarray(reverse(char(code(local!data)))) = local!data,
    concat(local!data, " is palindrome"),
    concat(local!data, " is not a palindrome")
  )
)
```
"Malayalam is palindrome"
