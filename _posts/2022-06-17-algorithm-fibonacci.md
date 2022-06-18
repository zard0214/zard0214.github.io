---


layout: post


title: Fibonacci


categories: Algorithms


tags: [dynamic-programming]


math: true


date: 2022-06-17 15:32 +0800


---


## Code
{% highlight java %}

    public static void main(String[] args) {
        System.out.println(fib(30));
        System.out.println(fibonacci(30));
    }

    //recursion
    public static int fib(int n) {
        if(n < 2) return n;
        int prev = 0, cur = 1;
        for (int i = 2; i <= n; i++) {
            int sum = prev + cur;
            prev = cur;
            cur = sum;
        }
        return cur;
    }

    public static int fibonacci(int n) {
        int dp[] = new int[n + 1];
        return fibonacci(dp, n);
    }

    private static int fibonacci(int[] dp, int n) {
        if(n < 2) return n;
        dp[n] =  fibonacci(dp, n - 1) + fibonacci(dp, n - 2);
        return dp[n];
    }

{% endhighlight %}
