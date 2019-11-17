---
title: 测试发博客
date: 2019-11-17 17:32:29
tags:
---
## 标题
正文
```java
public void mergeSort(int[] arr) {
	mergeSort(arr, 0, arr.length - 1);
}

public void mergeSort(int[] arr, int l, int r) {
	if(l<=r) return;
	int mid = l + (r-l) / 2;
	mergeSort(arr, l, mid);
	mergeSort(arr, mid+1, r);
	if(arr[mid] > arr[mid+1])
		merge(arr, l, mid, r);
}

public void merge(int[] arr, int l, int r) {
	int[] aux = new int[r-l+1];
	for(int i=l;i<=r;i++) {
		aux[i-l] = arr[i];
	}
	int i = l;
	int j = mid+1;
	for(int k=l;k<=r;k++) {
		if(i>mid) {
			arr[k] = aux[j-l];
			j++;
		} else if(j>r) {
			arr[k] = aux[i-l];
			i++;
		} else if(aux[i-l] > aux[j-l]) {
			arr[k] = aux[j-l];
			j++;
		} else {
			arr[k] = aux[i-l];
			i++;
		}
	}
}
```

