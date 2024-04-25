# Interleave strings challenge

Given `A`, `B` and `C` strings, find whether `C` is formed by the interleaving of `A` and `B`.

In other words, check whether `C` is totally formed by consuming the chars **in sequence** from `A` and `B`  (it doesn't matter if from `A` or `B` first).
It is not necessary to consume all chars from `A` and `B`.

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
- `A` = `"zzyxxy"`
- `B` = `"wyyxz"`
- `C` = `"zzwyyxyxzx"`

Output: `true`
    
Explanation:

`C` = `"zz"` from `A` + `"wyyx"` from `B` + `"yx"` from `A` + `"z"` from `B` + `"x"` from `A`

```
C = zz wyyx yx z x
    └┘ └──┘ └┘ ╵ ╵
    1   2   3  4 5

A = zz yx x y
    └┘ └┘ ╵
    1  3  5

B = wyyx z
    └──┘ ╵
     2   4
```

Note that `A` still have `"y"` left, which is not a problem.

### 2
Input:
- `A` = `"zzyxxy"`
- `B` = `"wyyxz"`
- `C` = `"wyyzzwyx"`

Output: `false`

Explanation:

`C` != `"wyy"` from `B` + `"zz"` from `A` + `"w"` from ? (there is no `"w"` as next char in `A` or `B`)

```
C = wyy zz w yx
    └─┘ └┘ ╵
     1  2  3


A = zz yxxy
    └┘
    2

B = wyy x z
    └─┘
     1
```

### 3
Input:
- `A` = `"zzyxxy"`
- `B` = `"wyyxz"`
- `C` = `"wzzyxxy"`

Output: `true`

Explanation:

`C` = `"w"` from `B` + `"zzyxxy"` from `A`

```
C = w zzyxxy
    ╵ └────┘
    1   2

A = zzyxxy
    └────┘
      2   

B = w y yxz
    ╵
    1
```

### 4 (try it)
Input:
- `A` = `"zzyxxy"`
- `B` = `"wyyxz"`
- `C` = `"wyyzzyxxz"`

Output: ?
