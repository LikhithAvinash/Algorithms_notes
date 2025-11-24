## Encode & Decode

## ⚡ Efficent Solution

```python

	class Solution:

    def encode(self, strs: List[str]) -> str:
        res = ""

        for s in strs:
            res += str(len(s))+"#"+s

        return res

    def decode(self, s: str) -> List[str]:

        res,i = [],0

        while i < len(s):

            j = i

            while s[j] != '#':
                j += 1

            length = int(s[i:j])

            res.append(s[j+1:j+1+length])

            i = j + 1 + length
            

        return res

## Space Complexity: O(n)
```
| Approach       | Time Complexity | Space Complexity |
|----------------|-----------------|------------------|
| Brute Force    | O(n+m)          | O(n)             |
| Hashmap        | O(n+m)          | O(n)             |



<details>
<summary>Approach</summary>

    1) Here I Encoded by length of the character from the given List- len(word) + #(seperate the string and the length) + s(main one)
    2) decode function gives the encoded one.....
    3) Till I find hash I will count each character when I finally find the '#' the previous iterations gives me the number
    4) Here first find the length of the number ---> Then find the number --> int(s[i:j])--> assign it as length ---> length = s[i:j]
    5) a + 1 gives the next index of the string(a == j in this example)
    6) then simply res.append(s[a+1:a+1+length])
    7) Repeat it for all the entire string and return the appended list
    
</details>
