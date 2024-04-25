# Interleave strings challenge

Given `A`, `B` and `C` strings, find whether `C` is formed by the interleaving of `A` and `B`.

## Java
```java
boolean isInterleave(String A, String B, String C)
```

## Python
```python
# @param A: string
# @param B: string
# @param C: string
# @return a boolean
def isInterleave(A, B, C):
```

## Constraints
- 1 <= `length(A)`, `length(B)`, `length(C)` <= 150

## Examples

### 1
Input:
- `A` = `"aabcc"`
- `B` = `"dbbca"`
- `C` = `"aadbbcbcac"`

Output: `true`
    
Explanation:
`"aa"` (from `A`) + `"dbbc"` (from `B`) + `"bc"` (from `A`) + `"a"` (from `B`) + `"c"` (from `A`)

### 2
Input :
- `A` = `"aabcc"`
- `B` = `"dbbca"`
- `C` = `"aadbbbaccc"`

Output: `false`

Explanation:
`"aa"` (from `A`) + `"dbb"` (from `B`) + `"b"` (from `A`) + `"a"` (there is no `"a"` as next char in `A` or `B`)
