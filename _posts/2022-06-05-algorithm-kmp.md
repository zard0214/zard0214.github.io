---


layout: post


title: KMP Algorithm


categories: Algorithms


tags: pattern-searching


toc:  true


math: true


date: 2022-06-05 15:32 +0800


---

## Introduction

KMP algorithm is an improved string matching algorithm proposed by D.E.Knuth, J.H.Morris and V.R.Pratt, so people call it Knuth-Morris-Platt operation (KMP algorithm for short). The core of the KMP algorithm is to use the information after the matching failure to minimize the matching times between the pattern string and the main string to achieve the purpose of fast matching. The specific implementation is through a next() function (the next() function is calculated by the prefix table), and the function itself contains the local matching information of the pattern string. The time complexity of the KMP algorithm is O(m+n).


## Code
{% highlight java %}

public static void KMP(String txt, String pat) {
    int T = txt.length();
    int P = pat.length();
    int i = 0;
    int j = 0;
    int[] lsp = new int[P];
    computerLsp(lsp, pat, P);
    while (i < T) {
        if (txt.charAt(i) == pat.charAt(j)) {
            i++;
            j++;
        }
        if (j == P) {
            System.out.println(" Found pattern "
                    + "at index " + (i - j));
            j = lsp[j - 1];
        } else if (txt.charAt(i) != pat.charAt(j)
                && i <= T) {
            if (j != 0) {
                j = lsp[j - 1];
            } else {
                i++;
            }
        }
    }
}

private static void computerLsp(int[] lsp, String pat, int P) {
    int i = 0;
    int j = 1;
    while (j < P) {
        if (pat.charAt(i) == pat.charAt(j)) {
            i++;
            lsp[j] = i;
            j++;
        } else {
            if (i != 0) {
                i = lsp[i - 1];
            } else {
                lsp[i] = i;
                j++;
            }
        }
    }
    for (int k = 0; k < lsp.length; k++) {
        System.out.print(lsp[k]);
    }
}

{% endhighlight %}
