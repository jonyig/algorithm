## Description

Bubble sort is sort by comparing two target, and change them that right is small and left is big

- it will run (n) -1 times
- Time complexity is O(n^2)
- it is a stable sorting
- the sorting is good at data which is small data

## Drilling

```php
[5,4,3,2,1]
```

| example | 5 | 4 | 3 | 2 | 1 |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 5→ 1 step | 4 | 5 | 3 | 2 | 1 | 5 ←→ 4 |  |
| 5→ 2 step | 4 | 3 | 5 | 2 | 1 | 5 ←→ 3 |  |
| 5→ 3 step | 4 | 3 | 2 | 5 | 1 | 5 ←→ 2 |  |
| 5→ 5 step | 4 | 3 | 2 | 1 | 5 | 5 ←→ 1 | 4 ( n-1 ) |
| 4→ 1 step | 3 | 4 | 2 | 1 | 5 | 4 ←→ 3 |  |
| 4→ 2 step | 3 | 2 | 4 | 1 | 5 | 4 ←→ 2 |  |
| 4→ 3 step | 3 | 2 | 1 | 4 | 5 | 4 ←→ 1 | 3 ( n-2 ) |
| 3→ 1 step | 2 | 3 | 1 | 4 | 5 | 3 ←→ 2 |  |
| 3→ 2 step | 2 | 1 | 3 | 4 | 5 | 3 ←→ 1 | 2 ( n-3 ) |
| 2→ 1 step | 1 | 2 | 3 | 4 | 5 | 2 ←→ 1 | 1 ( n-4 ) |

```shell
// n = 5 
1 + 2 + 3 + 4  = 10

// n = 6
1 + 2 + 3 + 4 + 5  = 15

=> n X (n-1) / 2 = (n^2 - n) / 2
=> O(n^2)
```

Golang

```shell
func bubbleSort(target []int) []int {
	for i := 0; i < len(target)-1; i++ {
		for j := 0; j < len(target)-1; j++ {
			fmt.Println("Hello", j)
			if target[j] > target[j+1] {
				target[j], target[j+1] = target[j+1], target[j]
				continue
			}
			break

		}
	}
	return target
}

//https://go.dev/play/p/L8Xj8upfe5d
```

## Related

- [https://ithelp.ithome.com.tw/articles/10276184](https://ithelp.ithome.com.tw/articles/10276184)
- [http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm](http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm)
- [http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm](http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm)