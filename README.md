# assignment2-guntipally

# Satwika Reddy Guntipally

#### Bengaluru

#### Name of the restaraunt is lucky. <br> This restaraunt is on highway which is easy to commute.It is famous for hyderabadi biryani.

**The bewildered tourist was lost.**

**We camped by the brook.**

---
### **Directions from airport to restaraunt :**
1.  The nearby airport to the restaraunt is *Rajiv Gandhi International Airport*.
2. From the airport drive towards west from 100m and roundabout take the 3rd exit and drive to NH765 and drive for 20km.
3. At DRDL main road take the 3rd exit and drive onto bhairamalguda flyover.
4. After driving for around 6km turn to slight right onto Lbnagar underpass.
5. After driving for 4km getonto kamineni flyover.
6. After 4km we can see lucky restaurant towrads right.

### **Recommended Food Items:**
* **Main Course**
     * Chicken Biryani
     * Nalli ghost Biryani
     * Mutton Biryani
     * Boneless Chicken biryani

* **Starters**
     * Chicken 65
     * Manchuria
     * Chicken drumsticks
     * babycorn majestics

**[Link for my bio](AboutMe.md)**

---
### **Recommended Sports/Activities**
The following table gives an information about name of the sport,where it can be played and how much it costs if there are any equipments.

| Sport Name | Location | Amount |
| --- | --- | --- |
| Badminton | Newyork | $25 |
| Cricket | chicago | $30 |
| tennis | dallas | $50 |
| hockey | misssouri | $45 |
| badminton | Atlanta | $33 |

---
### **My favourite quotes**
> Fill your papers with the breathings of your heart. <br>  -*William Wordsworth*

> The wiset prophets make sure of the event first.      -*Horace Walpole*

---
>In computer science, divide and conquer is an algorithm design paradigm. A divide-and-conquer algorithm recursively breaks down a problem into two or more sub-problems of the same or related type, until these become simple enough to be solved directly. The solutions to the sub-problems are then combined to give a solution to the original problem.
<https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm>
```
int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}
int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
} 
```

<https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>
