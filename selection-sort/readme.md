## Description

Selection sort is sort by comparing two target, and pick them then wait  to change at last

- it will run (n) -1 times
- Time complexity is O(n^2)
- it is a unstable sorting
- the sorting is good at data which is small data

## Drilling

```shell
[4,3,6,5,2]

target => it is the smallest variable\
index => it is a position now
```

| example | 4 | 3 | 6 | 5 | 2 |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 4→ 1 step | 4 | 3 | 6 | 5 | 2 | target → 3, index →3 |  |  |
| 4→ 2 step | 4 | 3 | 6 | 5 | 2 | target → 3, index →6 |  |  |
| 4→ 3 step | 4 | 3 | 6 | 5 | 2 | target → 3, index →5 |  |  |
| 4→ 4 step | 2 | 3 | 6 | 5 | 4 | target → 2, index →2  |  ( n-1 ) | 2 ←→ 4 |
| 3→ 1 step | 2 | 3 | 6 | 5 | 4 | target → , index →6 |  |  |
| 3→ 2 step | 2 | 3 | 6 | 5 | 4 | target → , index →5 |  |  |
| 3→ 3 step | 2 | 3 | 6 | 5 | 4 | target → , index →4 |  ( n-2 ) |  |
| 6→ 1 step | 2 | 3 | 6 | 5 | 4 | target →5 , index →5 |  |  |
| 6→ 2 step | 2 | 3 | 4 | 5 | 6 | target →4 , index →4 |  ( n-3 ) | 6 ←→ 4 |
| 5→ 1 step | 2 | 3 | 4 | 5 | 6 | target → , index →6 |  ( n-4 ) |  |

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
func selectionSort(array []int) []int {

	for i := 0; i <= len(array)-1; i++ {
		target := i
		for j := i + 1; j <= len(array)-1; j++ {
			if array[target] > array[j] {
				target = j
			}
		}
		array[i], array[target] = array[target], array[i]
	}
	return array
}

//https://go.dev/play/p/5mTv_SyIuQ5
```

## Related

- [https://ithelp.ithome.com.tw/articles/10276184](https://ithelp.ithome.com.tw/articles/10276719)
- [http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm](http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm)
- [http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm](http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm)