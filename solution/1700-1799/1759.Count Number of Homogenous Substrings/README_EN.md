# [1759. Count Number of Homogenous Substrings](https://leetcode.com/problems/count-number-of-homogenous-substrings)

[中文文档](/solution/1700-1799/1759.Count%20Number%20of%20Homogenous%20Substrings/README.md)

## Description

<p>Given a string <code>s</code>, return <em>the number of <strong>homogenous</strong> substrings of </em><code>s</code><em>.</em> Since the answer may be too large, return it <strong>modulo</strong> <code>10<sup>9</sup> + 7</code>.</p>

<p>A string is <strong>homogenous</strong> if all the characters of the string are the same.</p>

<p>A <strong>substring</strong> is a contiguous sequence of characters within a string.</p>

<p>&nbsp;</p>

<p><strong class="example">Example 1:</strong></p>

<pre>

<strong>Input:</strong> s = &quot;abbcccaa&quot;

<strong>Output:</strong> 13

<strong>Explanation:</strong> The homogenous substrings are listed as below:

&quot;a&quot;   appears 3 times.

&quot;aa&quot;  appears 1 time.

&quot;b&quot;   appears 2 times.

&quot;bb&quot;  appears 1 time.

&quot;c&quot;   appears 3 times.

&quot;cc&quot;  appears 2 times.

&quot;ccc&quot; appears 1 time.

3 + 1 + 2 + 1 + 3 + 2 + 1 = 13.</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>

<strong>Input:</strong> s = &quot;xy&quot;

<strong>Output:</strong> 2

<strong>Explanation:</strong> The homogenous substrings are &quot;x&quot; and &quot;y&quot;.</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>

<strong>Input:</strong> s = &quot;zzzzz&quot;

<strong>Output:</strong> 15

</pre>

<p>&nbsp;</p>

<p><strong>Constraints:</strong></p>

<ul>
    <li><code>1 &lt;= s.length &lt;= 10<sup>5</sup></code></li>
    <li><code>s</code> consists of lowercase letters.</li>
</ul>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def countHomogenous(self, s: str) -> int:
        mod = 10**9 + 7
        i, n = 0, len(s)
        ans = 0
        while i < n:
            j = i
            while j < n and s[j] == s[i]:
                j += 1
            cnt = j - i
            ans += (1 + cnt) * cnt // 2
            ans %= mod
            i = j
        return ans
```

### **Java**

```java
class Solution {
    private static final int MOD = (int) 1e9 + 7;

    public int countHomogenous(String s) {
        int n = s.length();
        long ans = 0;
        for (int i = 0, j = 0; i < n; i = j) {
            j = i;
            while (j < n && s.charAt(j) == s.charAt(i)) {
                ++j;
            }
            int cnt = j - i;
            ans += (long) (1 + cnt) * cnt / 2;
            ans %= MOD;
        }
        return (int) ans;
    }
}
```

### **C++**

```cpp
class Solution {
public:
    const int mod = 1e9 + 7;

    int countHomogenous(string s) {
        int n = s.size();
        long ans = 0;
        for (int i = 0, j = 0; i < n; i = j) {
            j = i;
            while (j < n && s[j] == s[i]) ++j;
            int cnt = j -  i;
            ans += 1ll * (1 + cnt) * cnt / 2;
            ans %= mod;
        }
        return ans;
    }
};
```

### **Go**

```go
func countHomogenous(s string) (ans int) {
	n := len(s)
	const mod int = 1e9 + 7
	for i, j := 0, 0; i < n; i = j {
		j = i
		for j < n && s[j] == s[i] {
			j++
		}
		cnt := j - i
		ans += (1 + cnt) * cnt / 2
		ans %= mod
	}
	return
}
```

### **...**

```

```

<!-- tabs:end -->
