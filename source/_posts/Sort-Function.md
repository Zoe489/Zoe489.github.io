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

# 冒泡排序法
`
/*
	从底层开始冒泡，两两比较，小的放在前面，直到小泡泡
*/
function BubbleSort(arr) {
	if (arr.length == 0) {
		return 0;
	}
	let temp = 0;
	for(let i = 0; i < arr.length - 1; i++) { // i是顶层的泡泡，标记最小的值
		for(let j = arr.length - 2; j >= i; j--) { 
			if(arr[j] > arr[j+1]) {
				temp = arr[j];
				arr[j] = arr[j+1];
				arr[j+1] = temp;
			}
		}
	}
	return arr;
}
 `
# 插入排序法
 `
 /*
	1.默认第一个已经排好序
	2.依次将接下来的数与数组里的每个元素进行比较，若比前一个小
 */
 function InsertSort(arr) {
    	if (arr.length == 0) {
    	  return 0;
    	}
      let temp = 0;   // 存放当前元素
      for(let i = 1; i < arr.length; i++) {
        if(arr[i] < arr[i-1]) {
          temp = arr[i];
          let pre = i - 1;

          while(pre >= 0 && temp < arr[pre]) {
            arr[pre+1] = arr[pre];
            pre--;
          }
          arr[pre+1] = temp;
        }
      }
      return arr;
   }
   `