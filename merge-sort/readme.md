## Description

Merge sort part to one data

- Time complexity is O(n log n)
- the sorting is the fastest in the Internal sort

## Drilling

```shell
[4,3,6,5,2]
[4,3,6][5,2]
[4,3][6][5][2]
[4][3][6][5][2]
[3,4][6][2,5]
[3,4,6][2,5]
[2,3,4,5,6]
```

Golang

```shell
func mergeSort(array []int) []int {
	if len(array) < 2 {
		return array
	}
	middle := len(array) / 2
	return merge(mergeSort(array[:middle]), mergeSort(array[middle:]))
}

func merge(left []int, right []int) []int {
	var result []int

	r := 0
	l := 0

	for {
		if r > len(right)-1 && l > len(left)-1 {
			break
		}
		if r > len(right)-1 {
			result = append(result, left[l])
			l++
			continue
		}

		if l > len(left)-1 {
			result = append(result, right[r])
			r++
			continue
		}

		if left[l] > right[r] {
			result = append(result, right[r])
			r++
			continue
		} else {
			result = append(result, left[l])
			l++
			continue
		}
	}
	return result
}

//https://go.dev/play/p/A5d-i9UpaDc
```

## Related

- [https://ithelp.ithome.com.tw/articles/10276184](https://ithelp.ithome.com.tw/articles/10278179)
- [http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm](http://spaces.isu.edu.tw/upload/18833/3/web/sorting.htm)
- [https://blog.boot.dev/golang/merge-sort-golang/](https://blog.boot.dev/golang/merge-sort-golang/)