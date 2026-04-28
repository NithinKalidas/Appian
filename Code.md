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

Print * from 5 to 1 in descending order:
```javascript
a!localVariables(
  local!data: 5,
  a!forEach(
    enumerate(local!data),
    joinarray(repeat(local!data - fv!index + 1, "*"), "")
  )
)
```
```
*****
****
***
**
*
```

Palindrome Check
```javascript
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

To Check Even or Odd
```javascript
a!localVariables(
  local!data: { 2, 3, 56, 67, 78, 72, 68 },
  a!forEach(
    local!data,
    if(
      mod(fv!item, 2) = 0,
      concat(fv!item, " is even"),
      concat(fv!item, " is odd")
    )
  )
)
```

To Sort an Integer Field
```javascript
a!localVariables(
  local!data: { 2, 3, 56, 67, 78, 72, 68 },
  index(
    todatasubset(
      arrayToPage: a!forEach(local!data, { value: fv!item }),
      pagingConfiguration: a!pagingInfo(
        1,
        - 1,
        a!sortInfo(field: "value", ascending: false)
      )
    ).data,
    "value",
    null
  )
)
```
