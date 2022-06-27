## Description

Insertion sort is pick a value then comparing previous list an insert it to them

- it will run (n) -1 times
- Time complexity is O(n^2)
- it is a stable sorting
- the sorting is good at data which is small data

## Drilling

```shell
[4,3,6,5,2]

target => it is the target variable
index => it is a position now
```

| example | 4 | 3 | 6 | 5 | 2 |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 3→ 1 step | 4 | 3 | 6 | 5 | 2 |  | (n-1) | 3 → 4 |
| 6→ 1 step | 3 | 4 | 6 | 5 | 2 | target →3 , index →0 |  |  |
| 6→ 2 step | 3 | 4 | 6 | 5 | 2 | target →4 , index →1 |  |  |
| 6→ 3 step | 3 | 4 | 6 | 5 | 2 | target →2, index →2  | (n-2) | 6 → 6 |
| 5→ 1 step | 3 | 4 | 6 | 5 | 2 | target →3, index →0 |  |  |
| 5→ 2 step | 3 | 4 | 6 | 5 | 2 | target →4, index →1 |  |  |
| 5→ 3 step | 3 | 4 | 6 | 5 | 2 | target →4, index →2 |   |  |
| 5→ 4 step | 3 | 4 | 5 | 6 | 2 | target →4 , index→3 | (n-3) | 5 → 6 |
| 2→ 1 step | 3 | 4 | 5 | 6 | 2 | target → , index →0 |  |  |
| 5→ 1 step | 2 | 3 | 4 | 5 | 6 | target → , index →1 | (n-1) | 2 → 3 |

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
func insertionSort(array []int) []int {
	for i := 0; i <= len(array)-1; i++ {

		for j := 0; j <= len(array)-1; j++ {
			if array[i] < array[j] {
				array[i], array[j] = array[j], array[i]
				continue
			}
			if i == j {
				break
			}
		}
	}
	return array
}

//https://go.dev/play/p/FklpOu6X-Cl
```

## Related

- [https://ithelp.ithome.com.tw/articles/10276184](https://ithelp.ithome.com.tw/articles/10277360)
- [http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm](http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm)
- [http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm](http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm)