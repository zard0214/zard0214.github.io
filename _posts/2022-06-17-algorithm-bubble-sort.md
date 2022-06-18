---


layout: post


title: Bubble-sort


categories: Algorithms


tags: sorting


math: true

date: 2022-06-17 15:32 +0800


---

## Introduction


## Code

{% highlight java %}

    public static void main(String[] args) {
        int arr[] = {64, 34, 25, 12, 22, 11, 90};
        AlgorithmBubbleSort.Solution.bubbleSort(arr);
        AlgorithmBubbleSort.Solution.printArray(arr);

    }

    public static class Solution {

        public static void bubbleSort(int[] arr) {
            int n = arr.length;
            for (int i = 0; i < n - 1; i++)
                for (int j = 0; j < n - i - 1; j++)
                    if (arr[j] > arr[j + 1]) {
                        // swap arr[j+1] and arr[j]
                        int temp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = temp;
                    }
        }

        /* Prints the array */
        public static void printArray(int arr[]) {
            int n = arr.length;
            for (int i=0; i<n; ++i)
                System.out.print(arr[i] + " ");
            System.out.println();
        }
    }

{% endhighlight %}
