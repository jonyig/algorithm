## Description

Quick sort set a pivot, and find left and right index, left is greater than pivot, right is less than pivot, then they change each other
if they are in the same index, change with pivot

if they are adjacent, change each other, and right index change with pivot

- Time complexity is O(n^2)
- it is a unstable sorting
- the sorting is the fastest in the Internal sort

## Drilling

```shell
[4,3,6,5,2]

left => it is greater than povit
right => it is less than povit
```

| pivot | 4 | 3 | 6 | 5 | 2 |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 6 | 4 | 3 | 6 | 5 | 2 | left ⇒ 6, right ⇒ 2 |  |  |
| 6 | 4 | 3 | 2 | 5 | 6 | left ⇒ 6, right ⇒ 2 |  | 6 ←→2 |
| 3 | 4 | 3 | 2 | 5 | 6 | left ⇒ 4, right ⇒ 2 |  |  |
| 3 | 2 | 3 | 4 | 5 | 6 | left ⇒ 4, right ⇒ 2 |  | 4 ←→2 |

```shell
worst case   O(n^2) 
Average case O(NlogN)
```

Golang

```shell
func insertionSort(array []int, left int, right int) []int {
	pivot := array[(left+right)>>1]
	l := left
	r := right
	if r > l {
		for {
			for array[l] < pivot {
				l++
			}

			for array[r] > pivot {
				r--
			}

			array[l], array[r] = array[r], array[l]

			if l >= r {
				break
			}
		}

		insertionSort(array, left, l-1)
		insertionSort(array, r+1, right)
	}
	return array
}

//https://go.dev/play/p/k-w6sv7l-qT
```

## Related

- [https://ithelp.ithome.com.tw/articles/10276184](https://ithelp.ithome.com.tw/articles/10278644)
- [http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm](http://www.chwa.com.tw/TResource/HS/book2/ch7/7-5.htm)
- [http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm](http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm)