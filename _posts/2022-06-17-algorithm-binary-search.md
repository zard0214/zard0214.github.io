---


layout: post


title: Binary-search


categories: Algorithms


tags: searching


math: true


toc:  true


date: 2022-06-17 15:32 +0800


---

## Introduction

The data should be sorted

## Code

{% highlight java %}

    public static void main(String[] args) {
        int array[] = {0,1,3,5,6,8,10};
        System.out.println(bisection(array, 0, array.length - 1, 6));
    }

    static int binarySearch(int arr[], int l, int r, int x) {
        if (r >= l) {
            int mid = l + (r - l) / 2;
            if (arr[mid] == x)
                return mid;
            if (arr[mid] > x)
                return binarySearch(arr, l, mid - 1, x);
            return binarySearch(arr, mid + 1, r, x);
        }
        return -1;
    }

    static int bisection(int array[], int left, int right, int k){
        int m = (left + right) / 2;
        if(left > right){
            return  - 1;
        }
        if(array[m] == k){
            return m;
        }else{
            if(array[m] < k){
                return bisection(array, m + 1, right, k);
            }else{
                return bisection(array, left, m - 1, k);
            }
        }
    }

{% endhighlight %}
