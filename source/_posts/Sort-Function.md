---
title: 排序算法
date: 2017-07-21 16:35:40
tags:
---
# 二分查找法
`
	function binarysearch(arr, target) {
	if(arr.length == 0) {
		return 0;
	}
	let low = 0;
	let high = arr.length;
	let mid;
	while(low <= high) {
		mid = Math.floor((high-low)/2);
		if(target == arr[mid]) {
			return mid;
		} else if (target < arr[mid]) {
			high = mid - 1;
		} else {
			low = mid + 1;
		}
	}
	return 0;
}
`