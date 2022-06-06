---


layout: post


title: Kadane's Algorithm


categories: Algorithms


tags: dynamic-programming


math: true


date: 2022-06-05 15:32 +0800


---


## Code
{% highlight java %}

    public static int maxSubArray(int[] nums) {
        int curMax  = nums[0];
        int max = nums[0];
        for (int i = 1;i < nums.length; i++) {
            curMax = Math.max(nums[i], curMax + nums[i]);
            max = Math.max(max, localMax);
        }
        return max;
    }

{% endhighlight %}


